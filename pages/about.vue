<template>
  <v-row>
    <v-col class="text-center">
        <h1 class="pa-16">
        About Page
      </h1>
      <p>This is a about page</p>

    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'about',
    head () {
    return {
      title: "About Page",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best Place for corny jokes"
        }
        

      ]
    }
    
  }
}
</script>
