<template>
  <v-layout
    justify-center
    align-center>
    <v-flex>
      <div class="text-xs-center">
      </div>
      <div id="cards" v-for="ferry in ferries" :key="ferry.id">
        <Card
          :name="ferry.VesselName"
          :id="ferry.VesselID"
          :latitude="ferry.Latitude"
          :longitude="ferry.Longitude"
          :ArrivingTerminalName="ferry.ArrivingTerminalName"
          :DepartingTerminalName="ferry.DepartingTerminalName"
          :EtaBasis="ferry.EtaBasis"
  />
      </div>
  
    </v-flex>
  </v-layout>
</template>

<script>
import Card from "~/components/Card.vue";
import axios from "axios";

export default {
  components: {
    Card
  },
  asyncData() {
    return axios
      .get(
        "http://www.wsdot.wa.gov/Ferries/API/Vessels/rest/vessellocations?apiaccesscode=80e61cf4-541b-4651-8228-6376d80567f7"
      )
      .then(response => {
        return {
          ferries: response.data
        };
      });
  }
};
</script>
<style scoped>
#cards {
  margin: auto;
  padding: 20px;
}
</style>

