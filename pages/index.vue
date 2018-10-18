<template>
  <v-layout
    column
    justify-center
    align-center>
    <v-flex
      xs12
      sm8
      md6>
      <div class="text-xs-center">
      </div>
      <div v-for="ferry in ferries" :key="ferry.id">
        <Card
          :name="ferry.name"
          :id="ferry.id"
          :latitude="ferry.latitude"
          :longitude="ferry.longitude"
  />
      </div>
  
    </v-flex>
  </v-layout>
</template>

<script>
import Card from '~/components/Card.vue'
import axios from 'axios';

export default {

  components: {
    Card
  },
  asyncData(){
    return axios.get("http://www.wsdot.wa.gov/Ferries/API/Vessels/rest/vessellocations?apiaccesscode=80e61cf4-541b-4651-8228-6376d80567f7").then((response)=>{
      return{
        ferries: response.data
      };
    });
  }
}
</script>
