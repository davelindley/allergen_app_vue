<template>
  <v-container>
  <v-layout row wrap>

        <v-flex xs6>
            <v-switch
                v-model="filters.Vegetarian"
                :label="`Vegetarian: ${filters.Vegetarian.toString()}`"
              ></v-switch>
        </v-flex>

  </v-layout>




  <v-data-table
    :headers="headers"
    :items="filteredItems"
    class="elevation-1"
  >
    <template v-slot:items="props">
      <td class="text-md-right">{{ props.item.name }}</td>
      <td class="text-xs-center">{{ props.item.calories }}</td>
      <td class="text-xs-center">
        <span><v-icon>{{ props.item.Vegetarian ?  'done_outline' : '' }}</v-icon></span>
      </td>
      <td class="text-xs-center">
        <span><v-icon>{{ props.item.Vegan ?  'done_outline' : '' }}</v-icon></span>
        </td>
      <td class="text-xs-center">
        <span><v-icon>{{ props.item.GlutenFree ?  'done_outline' : '' }}</v-icon></span>
      </td>
      <td class="text-xs-center">
        <span><v-icon>{{ props.item.DairyFree ?  'done_outline' : '' }}</v-icon></span>
      </td>
    </template>
    </v-data-table>
    </v-container>
</template>

<script>
  export default {
     data () {
         return {
             filters:{
             Vegetarian: true},
             headers: [
                 {
                     text: 'Item Name',
                     align: 'right',
                     sortable: false,
                     value: 'name'
                 },
                 {text: 'Calories', value: 'calories', align: 'center'},
                 {text: 'Vegetarian', value: 'Vegetarian', align: 'center'},
                 {text: 'Vegan', value: 'Vegan', align: 'center'},
                 {text: 'Gluten Free', value: 'GlutenFree', align: 'center'},
                 {text: 'Dairy Free', value: 'DairyFree', align: 'center'}
             ],
             food: [
                 {
                     name: 'Cheese Burger',
                     calories: 159,
                     Vegetarian: false,
                     Vegan: false,
                     GlutenFree: true,
                     DairyFree: false
                 },
                 {
                     name: 'Pulled Pork Nachos',
                     calories: 237,
                     Vegetarian: false,
                     Vegan: false,
                     GlutenFree: false,
                     DairyFree: true
                 },
                 {
                     name: 'Eclair',
                     calories: 262,
                     Vegetarian: false,
                     Vegan: 23,
                     GlutenFree: 6.0,
                     DairyFree: '7%'
                 },
                 {
                     name: 'Cupcake',
                     calories: 305,
                     Vegetarian: true,
                     Vegan: 67,
                     GlutenFree: 4.3,
                     DairyFree: '8%'
                 },
                 {
                     name: 'Gingerbread',
                     calories: 356,
                     Vegetarian: true,
                     Vegan: 49,
                     GlutenFree: 3.9,
                     DairyFree: '16%'
                 },
                 {
                     name: 'Jelly bean',
                     calories: 375,
                     Vegetarian: true,
                     Vegan: 94,
                     GlutenFree: 0.0,
                     DairyFree: '0%'
                 },
                 {
                     name: 'Lollipop',
                     calories: 392,
                     Vegetarian: true,
                     Vegan: 98,
                     GlutenFree: 0,
                     DairyFree: '2%'
                 },
                 {
                     name: 'Honeycomb',
                     calories: 408,
                     Vegetarian: false,
                     Vegan: 87,
                     GlutenFree: 6.5,
                     DairyFree: '45%'
                 },
                 {
                     name: 'Donut',
                     calories: 452,
                     Vegetarian: true,
                     Vegan: 51,
                     GlutenFree: 4.9,
                     DairyFree: '22%'
                 },
                 {
                     name: 'KitKat',
                     calories: 518,
                     Vegetarian: true,
                     Vegan: 65,
                     GlutenFree: 7,
                     DairyFree: '6%'
                 }
             ]
         }
     },
      computed:{
         filteredItems: function(){
             return this.food.filter((item) => (item.Vegetarian === this.filters.Vegetarian || this.filters.Vegetarian === false))
         }
      }
  }

</script>

<style>

</style>
