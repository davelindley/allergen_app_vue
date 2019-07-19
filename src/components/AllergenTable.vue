<template>
  <div>
    <v-layout row wrap>
      <v-flex xs6 align="center">
        <v-switch v-model="filters.Vegetarian" :label="`Vegetarian`"></v-switch>
      </v-flex>
      <v-flex xs6 align="center">
        <v-switch v-model="filters.Vegan" :label="`Vegan`"></v-switch>
      </v-flex>

      <v-flex xs6 lg2 md3>
        <v-switch v-model="filters.Gluten" :label="`Gluten`"></v-switch>

        <v-switch v-model="filters.Seafood" :label="`Seafood`"></v-switch>
      </v-flex>
      <v-flex xs6 lg2 md3>
        <v-switch v-model="filters.Lactose" :label="`Lactose`"></v-switch>

        <v-switch v-model="filters.Milk" :label="`Milk`"></v-switch>
      </v-flex>
      <v-flex xs6 lg2 md3>
        <v-switch v-model="filters.Peanut" :label="`Peanut`"></v-switch>

        <v-switch v-model="filters.Shellfish" :label="`ShellFish`"></v-switch>
      </v-flex>
      <v-flex xs6 lg2 md3>
        <v-switch v-model="filters.TreeNut" :label="`Tree Nut`"></v-switch>

        <v-switch v-model="filters.Wheat" :label="`Wheat`"></v-switch>
      </v-flex>
    </v-layout>

    <v-data-table :headers="headers" :items="filteredItems" item-key="name">
      <template v-slot:no-data>
        <v-alert :value="true" color="error" icon="warning">
          Sorry, nothing to display here :(
        </v-alert>
      </template>
      <template v-slot:items="props">
        <td class="text-md-right">{{ props.item.name }}</td>
        <td class="text-xs-center">{{ props.item.calories }}</td>
        <td class="text-xs-center">
          <span
            ><v-icon>{{
              props.item.Vegetarian ? "done_outline" : ""
            }}</v-icon></span
          >
        </td>
        <td class="text-xs-center">
          <span
            ><v-icon>{{ props.item.Vegan ? "done_outline" : "" }}</v-icon></span
          >
        </td>

        <td class="text-xs-center">
          <span
            ><v-icon>{{
              props.item.Gluten ? "done_outline" : ""
            }}</v-icon></span
          >
        </td>

        <td class="text-xs-center">
          <span
            ><v-icon>{{
              props.item.Seafood ? "done_outline" : ""
            }}</v-icon></span
          >
        </td>

        <td class="text-xs-center">
          <span
            ><v-icon>{{
              props.item.Lactose ? "done_outline" : ""
            }}</v-icon></span
          >
        </td>

        <td class="text-xs-center">
          <span
            ><v-icon>{{ props.item.Milk ? "done_outline" : "" }}</v-icon></span
          >
        </td>

        <td class="text-xs-center">
          <span
            ><v-icon>{{
              props.item.Peanut ? "done_outline" : ""
            }}</v-icon></span
          >
        </td>

        <td class="text-xs-center">
          <span
            ><v-icon>{{
              props.item.Shellfish ? "done_outline" : ""
            }}</v-icon></span
          >
        </td>

        <td class="text-xs-center">
          <span
            ><v-icon>{{
              props.item.TreeNut ? "done_outline" : ""
            }}</v-icon></span
          >
        </td>

        <td class="text-xs-center">
          <span
            ><v-icon>{{ props.item.Wheat ? "done_outline" : "" }}</v-icon></span
          >
        </td>
      </template>
    </v-data-table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      search: "",
      filters: {
        Vegetarian: false,
        Vegan: false,

        Gluten: false,
        Seafood: false,

        Lactose: false,
        Milk: false,

        Peanut: false,
        Shellfish: false,

        TreeNut: false,
        Wheat: false
      },
      headers: [
        {
          text: "Item Name",
          align: "right",
          sortable: false,
          value: "name",
          fixed: true,
          width: "100px"
        },
        { text: "Calories", value: "calories", align: "center" },
        { text: "Vegetarian", value: "Vegetarian", align: "center" },
        { text: "Vegan", value: "Vegan", align: "center" },
        { text: "Gluten", value: "Gluten", align: "center" },
        { text: "Seafood", value: "Seafood", align: "center" },
        { text: "Lactose", value: "Lactose", align: "center" },
        { text: "Milk", value: "Milk", align: "center" },
        { text: "Peanut", value: "Peanut", align: "center" },
        { text: "Shellfish", value: "Shellfish", align: "center" },
        { text: "Tree Nut", value: "TreeNut", align: "center" },
        { text: "Wheat", value: "Wheat", align: "center" }
      ],
      food: [
        {
          name: "Hot Dog",
          calories: 754,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: false,
          Milk: false,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "Chicken Tenders & Fries",
          calories: 581,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: false,
          Milk: false,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "Cheese Burger & Fries",
          calories: 882,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "16oz Peanuts",
          calories: 975,
          Vegetarian: true,
          Vegan: true,
          Gluten: false,
          Seafood: false,
          Lactose: false,
          Milk: false,
          Peanut: true,
          Shellfish: false,
          Treenut: false,
          Wheat: false
        },
        {
          name: "Bavarian Pretzel",
          calories: 808,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: false,
          Milk: false,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "Pepperoni Pizza",
          calories: 766,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: false,
          Milk: false,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "French Fries",
          calories: 943,
          Vegetarian: true,
          Vegan: true,
          Gluten: true,
          Seafood: false,
          Lactose: false,
          Milk: false,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "Cheese Pizza",
          calories: 935,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "Pretzel",
          calories: 793,
          Vegetarian: true,
          Vegan: true,
          Gluten: true,
          Seafood: false,
          Lactose: false,
          Milk: false,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "Dippin Dots Small",
          calories: 577,
          Vegetarian: true,
          Vegan: false,
          Gluten: false,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: false
        },
        {
          name: "Mr. Softee Soft Serve Cone",
          calories: 865,
          Vegetarian: true,
          Vegan: false,
          Gluten: false,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: false
        },
        {
          name: "Large Popcorn",
          calories: 533,
          Vegetarian: true,
          Vegan: false,
          Gluten: false,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: false
        },
        {
          name: "Buffalo Tenders & Fries",
          calories: 912,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: false,
          Milk: false,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "Short Rib Grilled Cheese",
          calories: 574,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "Mr. Softee Soft Serve Cup",
          calories: 887,
          Vegetarian: true,
          Vegan: false,
          Gluten: false,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: false
        },
        {
          name: "Pulled Pork Nacho",
          calories: 797,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "Dippin Dots Helmet",
          calories: 988,
          Vegetarian: true,
          Vegan: false,
          Gluten: false,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: false
        },
        {
          name: "Jumbo Dog",
          calories: 882,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: false,
          Milk: false,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "Dippin Dots Small Cup",
          calories: 763,
          Vegetarian: true,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: false,
          Milk: false,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "Nacho",
          calories: 797,
          Vegetarian: true,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: false
        },
        {
          name: "Dippin Dots Lol",
          calories: 502,
          Vegetarian: false,
          Vegan: false,
          Gluten: false,
          Seafood: false,
          Lactose: false,
          Milk: false,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: false
        },
        {
          name: "Corn Dog",
          calories: 897,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: false,
          Milk: false,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "RumFish Shrimp",
          calories: 530,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: true,
          Lactose: false,
          Milk: false,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "BBQ Pork Nachos",
          calories: 554,
          Vegetarian: false,
          Vegan: false,
          Gluten: false,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: false
        },
        {
          name: "Avenue Sunshine City Nachos",
          calories: 605,
          Vegetarian: false,
          Vegan: false,
          Gluten: false,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: false
        },
        {
          name: "Mr. Softee Soft Serve Helmet",
          calories: 647,
          Vegetarian: false,
          Vegan: false,
          Gluten: false,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: false
        },
        {
          name: "PC Sushi Bowl",
          calories: 961,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: false,
          Milk: false,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: false
        },
        {
          name: "Grilled Cheese",
          calories: 923,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "Beach Drive Cuban Sandwich",
          calories: 893,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        },
        {
          name: "Cheese Steak",
          calories: 539,
          Vegetarian: false,
          Vegan: false,
          Gluten: true,
          Seafood: false,
          Lactose: true,
          Milk: true,
          Peanut: false,
          Shellfish: false,
          Treenut: false,
          Wheat: true
        }
      ]
    };
  },
  computed: {
    filteredItems: function() {
      return this.food.filter(
        item =>
          (item.Vegetarian === this.filters.Vegetarian ||
            this.filters.Vegetarian === false) &&
          (item.Vegan === this.filters.Vegan || this.filters.Vegan === false) &&
          (item.Gluten === !this.filters.Gluten ||
            this.filters.Gluten === false) &&
          (item.Seafood === !this.filters.Seafood ||
            this.filters.Seafood === false) &&
          (item.Lactose === !this.filters.Lactose ||
            this.filters.Lactose === false) &&
          (item.Milk === !this.filters.Milk || this.filters.Milk === false) &&
          (item.Peanut === !this.filters.Peanut ||
            this.filters.Peanut === false) &&
          (item.Shellfish === !this.filters.Shellfish ||
            this.filters.Shellfish === false) &&
          (item.TreeNut === !this.filters.TreeNut ||
            this.filters.TreeNut === false) &&
          (item.Wheat === !this.filters.Wheat || this.filters.Wheat === false)
      );
    }
  }
};
</script>

<style></style>
