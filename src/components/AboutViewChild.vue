<template>
      <div v-for="(chef,index) in chefs" :key="index" class="cadre">
        <img :src="chef.image">
        <h2>{{chef.name}}</h2>
        <p>{{chef.p}}</p>
      </div>
      
</template>

<script>
export default {
  name: "AboutViewChild",
  data() {
    return {
      chefs: [
        {
          id:1,
          name: "Chef name",
          image: require("../assets/images/pngegg.png"),
          p:"Lorem ipsum dolor sit amet consectetur adipisicing elit.",
        },
        {
          id:2,
          name: "Chef name",
          image: require("@/assets/images/pngegg (1).png"),
          p:"Lorem ipsum dolor sit amet consectetur adipisicing elit.",
        },
        {
          id:3,
          name: "Chef name",
          image: require("@/assets/images/pngegg (2).png"),
          p:"Lorem ipsum dolor sit amet consectetur adipisicing elit.",
        },
        {
          id:4,
          name: "Chef name",
          image: require("@/assets/images/pngegg (3).png"),
          p:"Lorem ipsum dolor sit amet consectetur adipisicing elit.",
        },
      ],
    };
  },
};
</script>
