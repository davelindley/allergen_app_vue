<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Tropicana Field</span>
        <v-spacer></v-spacer>
        <span class="font-weight-light">ALLERGEN & DIETARY INFORMATION</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>

    </v-toolbar>

    <v-content>
      <AllergenTable/>
    </v-content>
  </v-app>
</template>

<script>
import AllergenTable from './components/AllergenTable'

export default {
  name: 'App',
  components: {
    AllergenTable
  },
  data () {
    return {
      //
    }
  }
}
</script>
