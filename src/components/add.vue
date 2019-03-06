<template>

</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      data: {
        id:'',
        first_name: "",
        last_name: "",
        email: "",
        gender: ""
      }
    };
  },
  methods: {
    Add() {
      let url = "https://test-data-2a788.firebaseio.com/data.json";
      axios.post(url, this.data).then(response => {
        console.log(response);
      });
    },
  }
};
</script>

<style>
</style>