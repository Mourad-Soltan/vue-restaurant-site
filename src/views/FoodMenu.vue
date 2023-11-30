<template>
  <h1>Food Menu</h1>
  <section class="FoodMenu">
    <FoodMenuChild></FoodMenuChild>
  </section>
  
</template>


<script>
// @ is an alias to /src
import FoodMenuChild from "@/components/FoodMenuChild.vue";

export default {
  name: "FoodMenu",
  components: {
    FoodMenuChild,
  },
};
</script>

<style>
h1{
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