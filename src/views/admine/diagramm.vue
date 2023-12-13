<template>
    <div class="admin">
        <div class="menu">
            <nav>
                <p><img src="@/assets/icons/tachometer-alt-solid.svg" alt="Dashboard Icon">Dashboard</p>
                <p><router-link to="admin">Home Page</router-link></p>
                <p><router-link to="orderList">Liste reservation commande</router-link></p>
            </nav>
        </div>
        <div class="charts">

            <div class="container-fluid pt-7 px-7">
                <div class="bg-secondary text-center rounded p-4">
                    <div class="d-flex align-items-center justify-content-between mb-4">
                        <h6 class="mb-0">Today's Table Reservation Metrics: Tracking Demand Trends in Our Restaurant</h6>
                    </div>
                    <div class="table-responsive">
                        <canvas id="myChart" width="200" height="200"></canvas>
                    </div>
                </div>
            </div>

            <h1>Food Chart</h1>

            <div class="container-fluid pt-7 px-7">
                <div class="bg-secondary text-center rounded p-4">
                    <div class="d-flex align-items-center justify-content-between mb-4">
                        <h6 class="mb-0">Today's Table Reservation Metrics: Tracking Demand Trends in Our Restaurant</h6>
                    </div>
                    <div class="table-responsive">
                        <canvas id="mySecondChart" width="200" height="200"></canvas>
                    </div>
                </div>
            </div>

        </div>
    </div>
</template>

<script>

import Chart from 'chart.js/auto';

export default {
  name: "diagramm",
  mounted() {
    const ctx = document.getElementById('myChart');
    const ctx2 = document.getElementById('mySecondChart');
    new Chart(ctx2, {
    type: 'bar',
    data: {
      labels: ['Food1', 'Food2', 'Food3', 'Food4', 'Food5', 'Food6', 'Food7', 'Food8', 'Food9', 'Food10', 'Food11', 'Food12'],
      datasets: [{
        label: '# Reservation per day',
        data: [12, 19, 3, 5, 2, 3, 2, 7, 9, 10, 2, 4],
        backgroundColor: 'rgba(255, 255, 255)',
        color: 'rgba(255, 255, 255)',
        borderColor: 'rgba(255, 128, 0)',
        borderWidth: 2
      }]
    },
  });
    new Chart(ctx, {
    type: 'line',
    data: {
      labels: [8, 10, 12, 14, 16, 18, 20],
      datasets: [{
        label: '# Reservation per day',
        data: [12, 19, 3, 5, 2, 3, 2],
        backgroundColor: 'rgba(255, 255, 255)',
        color: 'rgba(255, 255, 255)',
        borderColor: 'rgba(255, 128, 0)',
        borderWidth: 2
      }]
    },
    options: {
      scales: {
        y: {
          beginAtZero: true,
            grid: {
                    color: 'white', // Couleur de la ligne de repère horizontale
            },
            ticks: {
                    color: 'orange',  // Couleur des indices de repère sur l'axe x
            },
        },
        x: {
            beginAtZero: true,
            grid: {
                    color: 'white', // Couleur de la ligne de repère horizontale
            },
            ticks: {
                    color: 'orange',  // Couleur des indices de repère sur l'axe x
            },
        }
      }
    }
   });
  }
};

</script>

<style scoped>

h1{
  text-align: center;
  color: #F28D35;
  padding-bottom: 50px;
  padding-top: 50px
}

#myChart {
  margin-left: 80px;
  margin-right: 80px;
  padding-bottom: 100px;
  padding-top: 30px;
}

#mySecondChart {
  margin-left: 150px;
  margin-right: 100px;
  padding-bottom: 150px;
  padding-top: 30px;
}

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