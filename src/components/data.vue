 <!-- <template>
 <div>
    
       <div v-for="(d,index) in Info" :key="index">
   <center> <b-card bg-variant="info" text-variant="white" :title=d.content style="max-width: 540px;">
               <b-card title="Card Title"
          :img-src=d.image
          img-alt="Image"
          img-top
          tag="article"
          style="max-width: 20rem;"
          class="mb-2"
          >
  </b-card>
 
      <p class="card-text">{{d.data}}</p>
      <b-button href="#" variant="success">Share</b-button>
    </b-card>
    </center>
    <br>
    </div>
  </div> 
</template>-->

<script>
import axios from "axios";
export default {
  data() {
    return {
      Info: []
    };
  },
  mounted() {
    axios.get("https://test-data-2a788.firebaseio.com/data.json").then(response => {
      const data = response.data;
      for (let key in data) {
        const info = data[key];
        info.id = key;
        this.Info.push(info);
      }
    });
  }
};
</script>

<style>
</style>