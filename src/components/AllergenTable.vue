<template>
  <div>
  <v-layout row wrap>

        <v-flex xs6 align="center">

            <v-switch
                v-model="filters.Vegetarian"
                :label="`Vegetarian`"
              ></v-switch>
        </v-flex>
            <v-flex xs6 align="center">
            <v-switch
                v-model="filters.Vegan"
                :label="`Vegan`"
              ></v-switch>
            </v-flex>

        <v-flex xs6 lg2 md3>
            <v-switch
                v-model="filters.Gluten"
                :label="`Gluten`"
              ></v-switch>

            <v-switch
                v-model="filters.Dairy"
                :label="`Dairy`"
              ></v-switch>
        </v-flex>
      <v-flex xs6 lg2 md3>
            <v-switch
                v-model="filters.Lactose"
                :label="`Lactose`"
              ></v-switch>

            <v-switch
                v-model="filters.Milk"
                :label="`Milk`"
              ></v-switch>
        </v-flex>
      <v-flex xs6 lg2 md3>
            <v-switch
                v-model="filters.Peanut"
                :label="`Peanut`"
              ></v-switch>

            <v-switch
                v-model="filters.Shellfish"
                :label="`ShellFish`"
              ></v-switch>
        </v-flex>
      <v-flex xs6 lg2 md3>
            <v-switch
                v-model="filters.TreeNut"
                :label="`Tree Nut`"
              ></v-switch>

            <v-switch
                v-model="filters.Wheat"
                :label="`Wheat`"
              ></v-switch>
        </v-flex>


  </v-layout>



  <v-data-table
    :headers="headers"
    :items="filteredItems"
    item-key="name"
  >
      <template v-slot:no-data>
      <v-alert :value="true" color="error" icon="warning">
        Sorry, nothing to display here :(
      </v-alert>
    </template>
    <template v-slot:items="props" >
      <td class="text-md-right">{{ props.item.name }}</td>
      <td class="text-xs-center">{{ props.item.calories }}</td>
      <td class="text-xs-center">
        <span><v-icon>{{ props.item.Vegetarian ?  'done_outline' : '' }}</v-icon></span>
      </td>
      <td class="text-xs-center">
        <span><v-icon>{{ props.item.Vegan ?  'done_outline' : '' }}</v-icon></span>
        </td>

      <td class="text-xs-center">
        <span><v-icon>{{ props.item.Gluten ?  'done_outline' : '' }}</v-icon></span>
      </td>

      <td class="text-xs-center">
        <span><v-icon>{{ props.item.Dairy ?  'done_outline' : '' }}</v-icon></span>
      </td>

        <td class="text-xs-center">
        <span><v-icon>{{ props.item.Lactose ?  'done_outline' : '' }}</v-icon></span>
      </td>

        <td class="text-xs-center">
        <span><v-icon>{{ props.item.Milk ?  'done_outline' : '' }}</v-icon></span>
      </td>

        <td class="text-xs-center">
        <span><v-icon>{{ props.item.Peanut ?  'done_outline' : '' }}</v-icon></span>
      </td>

        <td class="text-xs-center">
        <span><v-icon>{{ props.item.Shellfish ?  'done_outline' : '' }}</v-icon></span>
      </td>

        <td class="text-xs-center">
        <span><v-icon>{{ props.item.TreeNut ?  'done_outline' : '' }}</v-icon></span>
      </td>

        <td class="text-xs-center">
        <span><v-icon>{{ props.item.Wheat ?  'done_outline' : '' }}</v-icon></span>
      </td>

    </template>
    </v-data-table>
    </div>
</template>

<script>
  export default {
     data () {
         return {
             search:'',
             filters:{
             Vegetarian: false,
             Vegan:false,

             Gluten:false,
             Dairy:false,

             Lactose:false,
             Milk:false,

             Peanut:false,
             Shellfish:false,

             TreeNut:false,
             Wheat:false},
             headers: [
                 {
                     text: 'Item Name',
                     align: 'right',
                     sortable: false,
                     value: 'name',
                     fixed:true,
                     width:"100px",
                 },
                 {text: 'Calories', value: 'calories', align: 'center'},
                 {text: 'Vegetarian', value: 'Vegetarian', align: 'center'},
                 {text: 'Vegan', value: 'Vegan', align: 'center'},
                 {text: 'Gluten', value: 'Gluten', align: 'center'},
                 {text: 'Dairy', value: 'Dairy', align: 'center'},
                 {text: 'Lactose', value: 'Lactose', align: 'center'},
                 {text: 'Milk', value: 'Milk', align: 'center'},
                 {text: 'Peanut', value: 'Peanut', align: 'center'},
                 {text: 'Shellfish', value: 'Shellfish', align: 'center'},
                 {text: 'Tree Nut', value: 'TreeNut', align: 'center'},
                 {text: 'Wheat', value: 'Wheat', align: 'center'},
             ],
             food: [
                 {
                     name: 'Cheese Burger',
                     calories: 159,
                     Vegetarian: true,
                     Vegan: true,
                     Gluten: true,
                     Dairy: true,
                     Lactose: true,
                     Milk: true,
                     Peanut:true,
                     Shellfish:true,
                     TreeNut:true,
                     Wheat:true
                 },
                 {
                     name: 'Pulled Pork Nachos',
                     calories: 237,
                     Vegetarian: false,
                     Vegan: false,
                     Gluten: false,
                     Dairy: false,
                     Lactose: false,
                     Milk: false,
                     Peanut:false,
                     Shellfish:false,
                     TreeNut:false,
                     Wheat:false
                 },
                 {
                     name: 'Eclair',
                     calories: 262,
                     Vegetarian: false,
                     Vegan: 23,
                     Gluten: false,
                     Dairy: true,
                     Lactose: false,
                     Milk: false,
                     Peanut:false,
                     Shellfish:false,
                     TreeNut:false,
                     Wheat:false
                 },
                 {
                     name: 'Cupcake',
                     calories: 305,
                     Vegetarian: true,
                     Vegan: true,
                     Gluten: true,
                     Dairy: false,
                     Lactose: false,
                     Milk: false,
                     Peanut:false,
                     Shellfish:false,
                     TreeNut:false,
                     Wheat:false
                 },
                 {
                     name: 'Gingerbread',
                     calories: 356,
                     Vegetarian: true,
                     Vegan: false,
                     Gluten: true,
                     Dairy: false,
                     Lactose: false,
                     Milk: false,
                     Peanut:false,
                     Shellfish:false,
                     TreeNut:false,
                     Wheat:false
                 },
                 {
                     name: 'Jelly bean',
                     calories: 375,
                     Vegetarian: true,
                     Vegan: false,
                     Gluten: false,
                     Dairy: false,
                     Lactose: false,
                     Milk: false,
                     Peanut:false,
                     Shellfish:false,
                     TreeNut:false,
                     Wheat:false
                 },
                 {
                     name: 'Lollipop',
                     calories: 392,
                     Vegetarian: true,
                     Vegan: true,
                     Gluten: true,
                     Dairy: false,
                     Lactose: false,
                     Milk: false,
                     Peanut:false,
                     Shellfish:false,
                     TreeNut:false,
                     Wheat:false
                 },
                 {
                     name: 'Honeycomb',
                     calories: 408,
                     Vegetarian: false,
                     Vegan: true,
                     Gluten: true,
                     Dairy: false,
                     Lactose: false,
                     Milk: false,
                     Peanut:false,
                     Shellfish:false,
                     TreeNut:false,
                     Wheat:false
                 },
                 {
                     name: 'Donut',
                     calories: 452,
                     Vegetarian: true,
                     Vegan: true,
                     Gluten: false,
                     Dairy: false,
                     Lactose: false,
                     Milk: false,
                     Peanut:false,
                     Shellfish:false,
                     TreeNut:false,
                     Wheat:false
                 },
                 {
                     name: 'KitKat',
                     calories: 518,
                     Vegetarian: true,
                     Vegan: true,
                     Gluten: true,
                     Dairy: false,
                     Lactose: false,
                     Milk: false,
                     Peanut:false,
                     Shellfish:false,
                     TreeNut:false,
                     Wheat:false
                 }
             ]
         }
     },
      computed:{
         filteredItems: function(){
             return this.food.filter((item) => (item.Vegetarian === this.filters.Vegetarian || this.filters.Vegetarian === false)
                                            && (item.Vegan === this.filters.Vegan || this.filters.Vegan === false)
                                         && (item.Gluten === !this.filters.Gluten || this.filters.Gluten === false)
                                         && (item.Dairy === !this.filters.Dairy || this.filters.Dairy === false)
                                         && (item.Lactose === !this.filters.Lactose || this.filters.Lactose === false)
                                         && (item.Milk === !this.filters.Milk || this.filters.Milk === false)
                                         && (item.Peanut === !this.filters.Peanut || this.filters.Peanut === false)
                                         && (item.Shellfish === !this.filters.Shellfish || this.filters.Shellfish === false)
                                         && (item.TreeNut === !this.filters.TreeNut || this.filters.TreeNut === false)
                                         && (item.Wheat === !this.filters.Wheat || this.filters.Wheat === false))
             }
      }
  }

</script>

<style>

</style>
