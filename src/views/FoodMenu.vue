<template>
  <h1 id="titre">Food Menu</h1>
  <section class="FoodMenu">
    <FoodMenuChild :foods="foods" @add="add" @del="del" @update-carte="update"></FoodMenuChild>
  </section>
  <section class="panier" v-if="paniers.length > 0">
    <div class="head">
      <h5>FOODS</h5>
      <h5>PRIX</h5>
      <h5>QUANTITÉ</h5>
      <h5>TOTAL</h5>
    </div>
    <hr>
    <br>
    <div v-for="(panier, index) in paniers" :key="index">
      <div class="body" v-if="panier.nborder > 0">
        <div class="profileFood">
          <img :src="panier.image">
          <h5>{{ panier.name }}</h5>
        </div>
        <h4>{{ panier.prix }}</h4>
        <div class="quatite">
          <h5>{{ panier.nborder }}</h5>
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
// @ is an alias to /src
import FoodMenuChild from "@/components/FoodMenuChild.vue";

export default {
  name: "FoodMenu",
  emits: ['add', 'del', 'update-carte'],
  components: {
    FoodMenuChild,
  },
  data() {
    return {
      cart: 1,
      foods: [
        {
          id: 0,
          name: "Food Name",
          image: require("../assets/images/food.jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
          prix: 15,
        },
        {
          id: 1,
          name: "Food Name",
          image: require("../assets/images/food(1).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
          prix: 15,
        },
        {
          id: 2,
          name: "Food Name",
          image: require("../assets/images/food(2).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
          prix: 15,
        },
        {
          id: 3,
          name: "Food Name",
          image: require("../assets/images/food(3).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
          prix: 15,
        },
        {
          id: 4,
          name: "Food Name",
          image: require("../assets/images/food(4).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
          prix: 15,
        },
        {
          id: 5,
          name: "Food Name",
          image: require("../assets/images/food(5).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
          prix: 15,
        },
        {
          id: 6,
          name: "Food Name",
          image: require("../assets/images/food(6).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
          prix: 15,
        },
        {
          id: 7,
          name: "Food Name",
          image: require("../assets/images/food(7).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
          prix: 15,
        },
        {
          id: 8,
          name: "Food Name",
          image: require("../assets/images/food(8).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
          prix: 15,
        },
        {
          id: 9,
          name: "Food Name",
          image: require("../assets/images/food(9).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
          prix: 15,
        },
        {
          id: 10,
          name: "Food Name",
          image: require("../assets/images/food(10).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
          prix: 15,
        },
        {
          id: 11,
          name: "Food Name",
          image: require("../assets/images/food(11).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
          prix: 15,
        },
      ],
      paniers: [],
    };
  },
  methods: {
    add(food) {
      //console.log(food.nborder);
      food.nborder++;
    },
    del(food) {
      //console.log(food.nborder);
      food.nborder--;
      if (food.nborder == 0) {
        for (let i = 0; i < this.paniers.length; i++) {
          if (this.paniers[i].id == food.id) {
            this.paniers.splice(i, 1);
          }
        }
      }
    },
    update(food) {
      for (let i = 0; i < this.paniers.length; i++) {
        if (this.paniers[i].id == food.id) {
          this.paniers.splice(i, 1);
        }
      }
      this.paniers.push(food);
      console.log(this.paniers);
    },
    calculatePrice(food) {
      return food.nborder * food.prix;
    },
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
#titre {
  text-align: center;
  color: #F28D35;
  padding-bottom: 100px;
}

.FoodMenu {
  display: grid;
  grid-template-columns: repeat(4, auto);
  gap: 40px;
  justify-content: center;
  padding-bottom: 100px;
}

.details {
  position: absolute;
  right: 0;
  bottom: 5px;
  height: 60px;
  text-align: center;
  text-transform: uppercase;
  background: #fff;
  bottom: 30px;
}

/*Image*/
.imgbox {
  position: absolute;
  top: 10px;
  left: 10px;
  bottom: 10px;
  right: 10px;
  background: #222;
  transition: 0.5s;
  z-index: 1;
}

.img {
  background: #4158D0;
  background-image: linear-gradient(45deg, #4158D0, #C850C0);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

/*Text*/
.title {
  font-weight: 600;
  font-size: 20px;
  color: #F2B035;
  background: #fff;
}

.head {
  display: grid;
  grid-template-columns: 5fr 1fr 1fr 1fr;
  gap: 50px;
  margin-bottom: -10px;
}

.panier {
  margin: 50px;
  padding: 20px;
  background-color: #ccc;
  border-radius: 20px;
}

.panier hr {
  border: 1px solid black;
  margin-bottom: 20px;
}

.body {
  padding-bottom: 50px;
  display: grid;
  grid-template-columns: 5fr 1fr 1fr 1fr;
  margin-top: -20px;
  gap: 50px;
}

.body h4 {
  margin-top: 10px;
}

.body img {
  width: 100px;
  border-radius: 20px;
}

.profileFood {
  display: grid;
  grid-template-columns: 2fr 3fr;
  gap: 20px;
}

.profileFood h5 {
  margin-top: 20px;
}

.quatite {
  display: grid;
  grid-template-columns: 15px 20px;
  gap: 5px;
  padding-left: 30px;
  margin-top: 10px;
}

.add_del {
  display: grid;
  grid-template-rows: 30px 5px;
  margin-top: -20px;
}

.add_del button {
  border: none;
  background-color: #ccc;
  cursor: pointer;
  font-size: 25px;
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
}

@media screen and (max-width : 1200px) {
  .FoodMenu {
    display: grid;
    grid-template-columns: repeat(2, auto);
    gap: 20px;
  }

  .Valide button {
    left: 70%;
  }

  .Valide span {
    left: 65%;
  }

  .panier * {
    font-size: 20px;
  }

  .add_del button {
    font-size: 20px;
  }


}

@media screen and (max-width : 600px) {

  .FoodMenu {
    display: grid;
    grid-template-columns: auto;
    gap: 10px;
  }

  .Valide button {
    left: 50%;
  }

  .Valide span {
    left: 45%;
  }

  .panier * {
    font-size: 15px;
  }

  .add_del button {
    font-size: 15px;
  }

  .profileFood h5 {
    margin-top: 10px;
  }
}</style>