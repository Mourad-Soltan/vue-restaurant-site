<template>
  <section class="presentation">
    <div>
      <div class="two">
        <h1>Enjoy
          <span>Delicious Food</span>
          in Your Healthy Life
        </h1>
      </div>
      <p>
        Indulge in the taste of prestige at our restaurant, where each dish is a culinary masterpiece,
         expertly crafted to tantalize your taste buds and provide an unforgettable gastronomic experience
      </p>
      <div>
        <button class="btn">
          <a class="animation" href="#"></a>
            Visit Now
          <a class="animation"></a>
        </button>
      </div>
    </div>
    <img src="@/assets/images/riz.png">
  </section>
</template>

<script>
export default {
  name: "HomePage",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>