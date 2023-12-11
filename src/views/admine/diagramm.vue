<template>
    <div class="admin">
        <menu></menu>
    </div>
</template>

<script>
// @ is an alias to /src
import menu from "@/components/admine/menu.vue";

export default {
  name: "diagramm",
  components: {
    menu,
  },
};

</script>

<style scoped>
.admin {
    margin-top: 16px;
    display: grid;
    grid-template-columns: 1.5fr 7fr;
}

.menu {
    padding: 20px;
    height: auto;
    background: gray;
}

.charts {
    padding: 20px;
}
img{
    width: 35px;
    height: 35px;
}
</style>
