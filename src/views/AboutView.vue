<template>
  <section class="presentation">
    <div>
      <h1>About Us</h1>
      <p>
        Welcome to Prestige du Goût, an exceptional culinary experience dedicated to awakening your taste buds and you
        to discover the quintessence of gastronomy. Since our opening, we have strived to create a place where
        refinement, creativity and passion come together to offer an unforgettable experience to our guests.
      </p>

      <p>
        At Prestige du Goût, each dish is a work of art carefully prepared by our talented chefs who
        share a common vision: to elevate cuisine to a level of excellence. We believe that every ingredient has
        its importance, and this is why we favor fresh, local and highest quality products to
        create flavors that transport you.
      </p>

      <p>
        Our dedicated team is committed to providing you with attentive and personalized service. Whether for an evening
        romantic, a special celebration or simply for a gastronomic experience, we are here to make
        each visit a celebration of gastronomy and pleasure.
      </p>
    </div>
    <img src="@/assets/images/chef.png">
  </section>
  <section class="chefs">
    <h1>Our Golden Chefs</h1>
    <div class="cadres">
      <AboutViewChild></AboutViewChild>
    </div>
  </section>
  <section class="story">
    <h1>Our Story</h1>
    <p>
      Plongez dans l'histoire de Prestige du Goût, une aventure culinaire qui a commencé avec une passion profonde pour
      l'art de la gastronomie. Fondé par le visionnaire Chef Pierre Leclerc, notre restaurant est bien plus qu'un lieu
      pour savourer des plats exceptionnels ; c'est une histoire de dévouement à la perfection culinaire.
    </p>

    <p>
      L'aventure a débuté dans une petite cuisine où le Chef Leclerc, guidé par son amour pour les ingrédients de qualité,
      a commencé à créer des expériences gustatives uniques. Rapidement, sa créativité a conquis les palais, et Prestige
      du Goût est devenu le rendez-vous des amateurs de cuisine raffinée de la région.
    </p>

    <p>
      Au fil des ans, notre restaurant s'est développé en un lieu empreint d'élégance et d'innovation. Chaque plat est une
      œuvre d'art, alliant traditions culinaires et techniques modernes. Notre équipe de chefs talentueux partage une
      passion commune pour l'excellence, cherchant constamment à émerveiller vos papilles.
    </p>

    <p>
      Aujourd'hui, Prestige du Goût est l'aboutissement d'une histoire riche en saveurs et en émotions. Nous vous invitons
      à faire partie de cette histoire, à explorer des menus exceptionnels, à créer des souvenirs autour d'une table
      magnifiquement dressée et à vivre l'essence de la gastronomie raffinée.
    </p>

    <p>
      Notre histoire continue avec chaque plat que nous servons, chaque sourire que nous accueillons et chaque moment
      partagé dans notre établissement. Merci de faire partie de cette aventure gourmande. Nous avons hâte de continuer à
      écrire notre histoire avec vous, nos précieux convives.
    </p>
  </section>
</template>

<script>
// @ is an alias to /src
import AboutViewChild from "@/components/AboutViewChild.vue";

export default {
  name: "HomeView",
  components: {
    AboutViewChild,
  },
};

</script>


<style>
.presentation {
  display: grid;
  grid-template-columns: 500px auto;
  justify-content: center;
  gap: 50px;
  margin-bottom: 100px;
}

.presentation img {
  height: 500px;
  ;
  width: 500px;
  margin-top: -50px;
}

.presentation h1 {
  font-size: 35px;
  color: #F28D35;
}

.presentation p {
  text-align: justify;
  line-height: 1.2;
}

.chefs h1 {
  text-align: center;
  font-size: 50px;
  color: #F28D35;
}

.cadres {
  display: grid;
  grid-template-columns: repeat(4, 300px);
  justify-content: center;
  gap: 50px;
  margin-top: 100px;
  margin-bottom: 150px;
}

.cadre {
  text-align: center;
  box-shadow: 20px;
  background: white;
  border-radius: 10px;
  transition: border-radius 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  box-shadow: 15px 15px 30px #bebebe,
    -15px -15px 30px #ffffff;
}

.cadre img {
  padding: 20px;
  width: 200px;
  height: 300px;
  background-color: white;
}

.cadre p,
h2 {
  background-color: white;
}

.cadre h2 {
  color: #F2B035;
}

.story {
  text-align: center;
  margin-bottom: 150px;
}

.story h1 {
  font-size: 50px;
  color: #F28D35;
}

.story p {
  text-align: center;
  margin-left: 100px;
  text-align: justify;
  margin-right: 100px;
}
</style>