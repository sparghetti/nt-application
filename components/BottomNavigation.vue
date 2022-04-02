<template>
  <v-bottom-navigation
    :value="value"
    color="primary"
  >
    <v-btn>
      <span style="font-weight: bold; font-size: 30px">+</span>
<!--      <v-icon style="font-weight: bolder">mdi-plus</v-icon>-->
    </v-btn>

    <v-btn>
      <v-icon>mdi-lead-pencil</v-icon>
    </v-btn>

    <v-btn>
      <v-icon>mdi-delete</v-icon>
    </v-btn>

    <v-btn>
      <v-icon>mdi-printer</v-icon>
    </v-btn>
  </v-bottom-navigation>
</template>

<script>
export default {
  data () {
    return {
      value: 0
    }
  }
}
</script>
