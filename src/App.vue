<template>
  <nav>
    <img src="@/assets/images/Prestige du Goût.png">
    <div class="menu">
      <router-link to="/" class="custom-link">Home</router-link>
      <router-link to="/About" class="custom-link">About</router-link>
      <router-link to="/FoodMenu" class="custom-link">Food Menu</router-link>
      <router-link to="/Reservation" class="custom-link">Reservation</router-link>
    </div>
    <div class="icon">
      <router-link to="/" class="custom-link"><img src="@/assets/icons/house-chimney-1.png"></router-link>
      <img src="@/assets/icons/cart.svg">
      <img src="@/assets/icons/search-alternate.png">
    </div>
  </nav>
  <hr>


  <router-view />

  <hr>
 
    
  <footer id="contact">
    <div class="footer">
      <div class="main">
        <div class="list">
          <h4>Quick Links</h4>
          <ul>
            <li><a href="#">Abous us</a></li>
            <li><a href="#">Terms & Conditions</a></li>
            <li><a href="#">Help</a></li>
            <li><a href="#">Tour</a></li>
          </ul>
        </div>
        <div class="list">
          <h4>Support</h4>
          <ul>
            <li><a href="#">Abous us</a></li>
            <li><a href="#">Terms & Conditions</a></li>
            <li><a href="#">Help</a></li>
            <li><a href="#">Tour</a></li>
          </ul>
        </div>
        <div class="list">
          <h4>Contact Info</h4>
          <ul>
            <li><a href="#">98 West 21th Street</a></li>
            <li><a href="#">New York NY 10016</a></li>
            <li><a href="#">+1(123)-456-7890</a></li>
            <li><a href="mailto:#">info@mydommain.com</a></li>
          </ul>
        </div>
        <div class="social">
          <h4>Connect</h4>
          <a href="#"><i class='bx bxl-facebook'></i></a>
          <a href="#"><i class='bx bxl-instagram'></i></a>
          <a href="#"><i class='bx bxl-twitter'></i></a>
          <a href="#"><i class='bx bx-link'></i></a>
        </div>
      </div>
    </div>
    <div class="end-text">
      <p>Copiright All rights reserved | Made with by Mourad Soltan TI15</p>
    </div>
  </footer>
</template>
<script>
export default {
  name: "app",
  components: {

  },
  data() {
    return {
      
    }
  },
  methods: {
  },
  computed: {
},
};
</script>


<style scoped>
a {
  text-decoration: none;
}

nav {
  display: grid;
  grid-template-columns: 3fr 4fr 1.5fr;
  padding: 20px;
  padding-bottom: -10px;
}

nav img {
  height: 100px;
  width: 120px;
  margin-left: 50px;
  margin-top: -40px;
}

.icon img {
  height: 22px;
  width: 22px;
  margin-top: 3px;
}

.menu {
  display: grid;
  grid-template-columns: 50px 50px 100px 50px;
  gap: 70px;
  font-size: 20px;
  color: black;
  margin-top: 3px;
}

.custom-link {
  text-decoration: none;
  color: inherit;
  font-weight: bold;
}

.custom-link:hover {
  color: #F28D35;
  transform: scale(1.1);
}

hr {
  border-color: #F28D35;
  margin-top: -15px;
  margin-bottom: 100px;
}

footer {
  margin-top: -100px;
}

ul {
  list-style-type: none;
}

.list {
  background-color: #FFE36B;
}

.footer {
  padding: 0px 50px;
  background-color: #FFE36B;
  padding-left: 200px;
}

.main {
  display: grid;
  grid-template-columns: repeat(4, auto);
  gap: 20px;
  background-color: #FFE36B;
}

.list h4 {
  font-size: 21px;
  color: #F28D35;
  margin-bottom: 30px;
  position: relative;
  background-color: #FFE36B;
}

.list h4:before {
  content: "";
  position: absolute;
  height: 2px;
  width: 60px;
  left: 0;
  bottom: -10px;
  background-color: #fff;
}

.list ul li {
  margin-bottom: 16px;
}

ul {
  padding: 0;
  margin: 0;
  background-color: #FFE36B;
}

.social,
.list ul li a {
  color: black;
  font-size: 18px;
  display: block;
  transition: .3s;
  background-color: #FFE36B;
}

.social,
.list ul li a:hover {
  transform: translateX(14px);
  background-color: #FFE36B;
}

.social a {
  height: 40px;
  width: 40px;
  background-color: #fff;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-size: 21px;
  border-radius: 15px;
  transition: .3s;
  margin-right: 10px;
  color: #F28D35;
}

.social a:hover {
  transform: scale(1.1);
}

.social h4 {
  background-color: #FFE36B;
  color: #F28D35;
}

.end-text {
  text-align: center;
  padding-top: 40px;
  color: #221314;
  font-size: 14px;
  letter-spacing: 2px;
  background-color: #FFE36B;
  padding-bottom: 50px;
}

.end-text p {
  background-color: #FFE36B;
}
</style>
