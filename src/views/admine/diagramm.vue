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
                      <canvas id="myChart" ></canvas>
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
  this.calculreservation();
  },
  methods:{
    loadDataFromLocalStorage() {
      const jsonData = localStorage.getItem("reservation");
      return jsonData ? JSON.parse(jsonData) : [];
    },
    countReservationsForDay(dayName) {
      const reservations = this.loadDataFromLocalStorage();
      const dayReservations = reservations.filter(reservation => {
        const reservationDay = new Date(reservation.date).toLocaleDateString('en-US', { weekday: 'long' });
        return reservationDay.toLowerCase() === dayName.toLowerCase();
      });
      return dayReservations.length;
    },
    calculreservation() {
      const reservationsMonday = this.countReservationsForDay('Monday');
      const reservationsTuesday = this.countReservationsForDay('Tuesday');
      const reservationsWednesday = this.countReservationsForDay('Wednesday');
      const reservationsThursday = this.countReservationsForDay('Thursday');
      const reservationsFriday = this.countReservationsForDay('Friday');
      const reservationsSaturday = this.countReservationsForDay('Saturday');
      const reservationsSunday = this.countReservationsForDay('Sunday');

      // Destroy the old chart
      if (this.myChart) {
        this.myChart.destroy();
      }

      // Create a new chart with updated data
      const ctx = document.getElementById('myChart');
      this.myChart = new Chart(ctx, {
        type: 'bar',
        data: {
          labels: ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday'],
          datasets: [{
            label: '# Reservation per day',
            data: [reservationsMonday, reservationsTuesday, reservationsWednesday, reservationsThursday, reservationsFriday, reservationsSaturday, reservationsSunday],
            backgroundColor: 'rgba(255, 181, 52)',
            borderWidth: 1
          }]
        },
        options: {
          scales: {
            x: {
              type: 'category',
              labels: ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday'],
            },
            y: {
              beginAtZero: true
            }
          }
        },
      });

      // Log the updated data
      //console.log(this.myChart.data.datasets[0].data);
    }
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