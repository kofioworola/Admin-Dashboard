<template>
  <v-container>
    <v-row>
      <v-col v-for="card in cards" :key="card.id">
        <v-card :class="`${card.color} mx-auto white--text`">
          <v-icon>mdi-icon </v-icon>

          My card
        </v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <v-data-table
          :headers="headers"
          :items="desserts"
          :items-per-page="5"
          class="elevation-1"
        ></v-data-table>
      </v-col>
      <v-col>
        <!-- <v-sparkline color="blue" :value="values" padding="20" height="200">
          <template v-slot:label="item"> N{{ item.value }} </template>
        </v-sparkline> -->
        <apexchart width="500" type="line" :options="chartOptions" :series="series"></apexchart>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import VueApexCharts from 'vue-apexcharts'
export default {
  data() {
    return {
      cards: [
        {
          id: 1,
          title: 'Wallet',
          icon: 'mdi-account',
          number: '100000',
          color: 'red',
        },
        {
          id: 2,
          title: 'Savings',
          icon: 'mdi-savings',
          number: '500000',
          color: 'purple',
        },
        {
          id: 3,
          title: 'Loan',
          icon: 'mdi-loan',
          number: '20000',
          color: 'blue',
        },
      ],
      headers: [
        {
          text: 'Dessert (100g serving)',
          align: 'start',
          sortable: false,
          value: 'name',
        },
        { text: 'Calories', value: 'calories' },
        { text: 'Fat (g)', value: 'fat' },
        { text: 'Carbs (g)', value: 'carbs' },
        { text: 'Protein (g)', value: 'protein' },
        { text: 'Iron (%)', value: 'iron' },
      ],
      desserts: [
        {
          name: 'Frozen Yogurt',
          calories: 159,
          fat: 6.0,
          carbs: 24,
          protein: 4.0,
          iron: '1%',
        },
        {
          name: 'Ice cream sandwich',
          calories: 237,
          fat: 9.0,
          carbs: 37,
          protein: 4.3,
          iron: '1%',
        },
        {
          name: 'Eclair',
          calories: 262,
          fat: 16.0,
          carbs: 23,
          protein: 6.0,
          iron: '7%',
        },
        {
          name: 'Cupcake',
          calories: 305,
          fat: 3.7,
          carbs: 67,
          protein: 4.3,
          iron: '8%',
        },
        {
          name: 'Gingerbread',
          calories: 356,
          fat: 16.0,
          carbs: 49,
          protein: 3.9,
          iron: '16%',
        },
        {
          name: 'Jelly bean',
          calories: 375,
          fat: 0.0,
          carbs: 94,
          protein: 0.0,
          iron: '0%',
        },
        {
          name: 'Lollipop',
          calories: 392,
          fat: 0.2,
          carbs: 98,
          protein: 0,
          iron: '2%',
        },
        {
          name: 'Honeycomb',
          calories: 408,
          fat: 3.2,
          carbs: 87,
          protein: 6.5,
          iron: '45%',
        },
        {
          name: 'Donut',
          calories: 452,
          fat: 25.0,
          carbs: 51,
          protein: 4.9,
          iron: '22%',
        },
        {
          name: 'KitKat',
          calories: 518,
          fat: 26.0,
          carbs: 65,
          protein: 7,
          iron: '6%',
        },
      ],
      values: [100, 1000, 50000, 3000],
      chartOptions: {
          chart: {
            id: 'vuechart-example'
          },
          xaxis: {
            categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998]
          }
        },
        series: [{
          name: 'series-1',
          data: [30, 40, 35, 50, 49, 60, 70, 91]
        }]
    }
  },
}
</script>