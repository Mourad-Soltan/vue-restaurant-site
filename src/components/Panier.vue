<template>
    <section class="panier card" v-if="paniers.length > 0">
        <div class="head">
            <h3>FOODS</h3>
            <h3>PRIX</h3>
            <h3>QUANTITÉ</h3>
            <h3>TOTAL</h3>
        </div>
        <hr>
        <br>
        <div v-for="(panier, index) in paniers" :key="index">
            <div class="body" v-if="panier.nborder > 0">
                <div class="profileFood">
                    <img :src="panier.image">
                    <h4>{{ panier.name }}</h4>
                </div>
                <h4>{{ panier.prix }}</h4>
                <div class="quatite">
                    <span>{{ panier.nborder }}</span>
                    <div class="add_del">
                        <button v-on:click="add(panier)">+</button>
                        <button v-if="panier.nborder > 0" v-on:click="del(panier)">-</button>
                        <button v-else style="cursor: no-drop;">-</button>
                    </div>
                </div>
                <h4>{{ calculatePrice(panier) }}</h4>
            </div>
        </div>
        <div class="Valide">
            <span>TOTAL : {{ tolat }}</span>
            <button class="add_to_order">Valider La Commande</button>
        </div>

    </section>
</template>

<script>
export default {
    name: "Panier",
    props: {
        paniers: {
            type: Array,
            required: true,
        }
    },
    data() {
        return {};
    },
    methods: {
        add(food) {
            //console.log(food.nborder);
            //food.nborder++;
            this.$emit('add', food);
        },
        del(food) {
            this.$emit('del', food);
        },
        update(food) {
            this.$emit('update', food);
        }
    },
    computed: {
        tolat() {
            let montants = 0;
            for (let i = 0; i < this.paniers.length; i++) {
                montants += (this.paniers[i].prix * this.paniers[i].nborder);
            }
            return montants
        }
    }
};
</script>

<style scoped>
.panier {
    margin: 50px;
    padding: 20px;
}

.panier hr {
    border: 1px solid #ccc;
    margin-bottom: 20px;

}

.body {
    padding-bottom: 50px;
    display: grid;
    grid-template-columns: 5fr 1fr 1fr 1fr;
    margin-top: -20px;
    gap: 50px;
}

.body img {
    width: 100px;
    border-radius: 20px;
}

.card {
    max-width: none;
    height: auto;
    background: white;
    border-radius: 10px;
    transition: border-radius 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.profileFood {
    display: grid;
    grid-template-columns: 2fr 3fr;

}

.quatite {
    display: grid;
    grid-template-columns: 15px 20px;
    gap: 5px;
    margin-top: 20px;
    padding-left: 30px;
}

.add_del {
    display: flex;
    flex-direction: column;
    margin-top: -10px;
}

.add_del button {
    border: none;
    background-color: white;
    cursor: pointer;
    font-size: 15px;
    font-weight: bold;
}

.Valide button {
    border: none;
    outline: none;
    background-color: #F28D35;
    padding: 10px 15px;
    font-size: 12px;
    font-weight: 700;
    color: #fff;
    border-radius: 5px;
    transition: all ease 0.1s;
    box-shadow: 0px 5px 0px 0px #FFE36B;
    position: relative;
    left: 82%;
}

.Valide button:active {
    transform: translateY(5px);
    box-shadow: 0px 0px 0px 0px #a29bfe;
}

.Valide span {
    position: relative;
    left: 80%;
}</style>
