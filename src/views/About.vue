<!--<template>
   <div><center>
    <b-card class="bv-example-row" bg-variant="info" text-variant="Dark"  style="max-width: 900px;">
    <b-row>
        <b-col></b-col>
        <b-col>
          หัวข้อ
           <b-form-input v-model="data.content" type="text" placeholder="Content"></b-form-input>
           <br>
           เนื้อหา
    <b-form-textarea
      id="textarea1"
      v-model="data.news"
      placeholder="news"
      :rows="3"
      :max-rows="6"
    ></b-form-textarea>
    <br>
    เพิ่มรูปภาพ
     <b-form-input v-model="data.image" type="text" placeholder="url"></b-form-input>
     <br>
    <button @click="Add">ADD</button>
        </b-col>
        <b-col></b-col>
    </b-row>
    </b-card>
</center>
  
  </div> 
  </template> -->

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
        alert('Add Success !!')
        this.data.id = ""
        this.data.first_name = ""
        this.data.last_name = ""
        this.data.email = ""
        this.data.gender = ""
      });

    }

  }
};
</script>

<style>
</style>