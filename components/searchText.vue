<template>
  <div>
    <form @input="onSubmit">
      <v-row class="d-flex flex-row align-center justify-center pb-10">
        <v-col cols="12" lg="6">
          <v-text-field
          clearable
          solo
          dense
          v-model="text"

            label="Search Joke..."
            
          ></v-text-field>
        </v-col>

      </v-row>
    </form>
  </div>
</template>

<script>
export default {
  name: "searchText",
  data() {
    return {
      text: "",
    };
  },
  methods: {
    onSubmit() {
      this.$emit("search-text", this.text);
      
    },
  },
};
</script>

<style>
</style>