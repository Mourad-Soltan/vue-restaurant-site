<template>
    <div v-for="(food, index) in foods" :key="index" class="card">
        <div class="imgbox">
            <img :src="food.image" class="img">
        </div>
        <div class="details">
            <h2 class="title">{{ food.name }}</h2>
            <span class="caption">{{ food.p }}</span>
        </div>
    </div>
</template>


<script>
export default {
    name: "FoodMenuChild",
    data() {
        return {
            foods: [
                {
                    id: 0,
                    name: "Food Name",
                    image: require("../assets/images/food.jpeg"),
                    p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                },
                {
                    id: 1,
                    name: "Food Name",
                    image: require("../assets/images/food(1).jpeg"),
                    p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                },
                {
                    id: 2,
                    name: "Food Name",
                    image: require("../assets/images/food(2).jpeg"),
                    p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                },
                {
                    id: 3,
                    name: "Food Name",
                    image: require("../assets/images/food(3).jpeg"),
                    p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                },
                {
                    id: 4,
                    name: "Food Name",
                    image: require("../assets/images/food(4).jpeg"),
                    p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                },
                {
                    id: 5,
                    name: "Food Name",
                    image: require("../assets/images/food(5).jpeg"),
                    p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                },
                {
                    id: 6,
                    name: "Food Name",
                    image: require("../assets/images/food(6).jpeg"),
                    p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                },
                {
                    id: 7,
                    name: "Food Name",
                    image: require("../assets/images/food(7).jpeg"),
                    p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                },
                {
                    id: 8,
                    name: "Food Name",
                    image: require("../assets/images/food(8).jpeg"),
                    p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                },
                {
                    id: 9,
                    name: "Food Name",
                    image: require("../assets/images/food(9).jpeg"),
                    p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                },
                {
                    id: 10,
                    name: "Food Name",
                    image: require("../assets/images/food(10).jpeg"),
                    p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                },
                {
                    id: 11,
                    name: "Food Name",
                    image: require("../assets/images/food(11).jpeg"),
                    p: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                },
            ],
        };
    },



}
</script>