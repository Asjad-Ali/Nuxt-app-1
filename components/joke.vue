<template>
<nuxt-link :to='id'>
  <v-card class="joke">
      <p>{{ joke }}</p>
  </v-card>
  </nuxt-link>
</template>

<script>
export default {
    name: "joke",
    props: ['joke', 'id']
}
</script>

<style>
.joke {
    padding: 1rem;
    border: 1px dotted  #ccc;
    margin: 1rem 0;
}
*{
    text-decoration: none;
}
</style>