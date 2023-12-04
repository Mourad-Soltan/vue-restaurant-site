<template>
  <h1>Food Menu</h1>
  <section class="FoodMenu">
    <FoodMenuChild :foods="foods" @add="add" @del="del" @update-carte="update"></FoodMenuChild>
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
        },
        {
          id: 1,
          name: "Food Name",
          image: require("../assets/images/food(1).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
        },
        {
          id: 2,
          name: "Food Name",
          image: require("../assets/images/food(2).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
        },
        {
          id: 3,
          name: "Food Name",
          image: require("../assets/images/food(3).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
        },
        {
          id: 4,
          name: "Food Name",
          image: require("../assets/images/food(4).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
        },
        {
          id: 5,
          name: "Food Name",
          image: require("../assets/images/food(5).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
        },
        {
          id: 6,
          name: "Food Name",
          image: require("../assets/images/food(6).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
        },
        {
          id: 7,
          name: "Food Name",
          image: require("../assets/images/food(7).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
        },
        {
          id: 8,
          name: "Food Name",
          image: require("../assets/images/food(8).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
        },
        {
          id: 9,
          name: "Food Name",
          image: require("../assets/images/food(9).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
        },
        {
          id: 10,
          name: "Food Name",
          image: require("../assets/images/food(10).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
        },
        {
          id: 11,
          name: "Food Name",
          image: require("../assets/images/food(11).jpeg"),
          p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          nborder: 0,
        },
      ],
      panier:[],
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
    },
    update(food) {
      for(let i=0;i<this.panier.length;i++){
        if(this.panier[i].nborder==food.nborder){
          this.panier.splice(i,1);
        }
      }
      this.panier.push(food);
      console.log(this.panier);
    },

  },
};
</script>

<style>
h1 {
  text-align: center;
  font-size: 45px;
  color: #F28D35;
  padding-bottom: 100px;
}

.FoodMenu {
  display: grid;
  grid-template-columns: repeat(4, auto);
  gap: 40px;
  justify-content: center;
  padding-bottom: 200px;
}

.card {
  overflow: visible;
  position: relative;
  width: 290px;
  height: 290px;
  background: #fff;
  box-shadow: 0 2px 10px rgba(0, 0, 0, .2);
  border-radius: 20px;
}

.card:before,
.card:after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 4px;
  background: #fff;
  transition: 0.5s;
  z-index: -99;
  border-radius: 20px;
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

.caption {
  font-weight: 500;
  font-size: 14px;
  color: black;
  display: block;
  margin-top: -7px;
  background: #fff;
  border-radius: 20px;
}

/*Hover*/
.card:hover .imgbox {
  bottom: 80px;
}

.card:hover:before {
  transform: rotate(20deg);
  border-radius: 20px;
}

.card:hover:after {
  transform: rotate(10deg);
  box-shadow: 0 2px 20px rgba(0, 0, 0, .2);
  border-radius: 20px;
}
</style>