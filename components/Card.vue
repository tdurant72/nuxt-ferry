<template>
<div>
  <v-layout>
    <v-flex xs12 sm6 offset-sm3>
      <v-card>
          <v-container fill-height fluid>
            <v-layout fill-height>
              <v-flex xs12 align-center flexbox>
                <span class="headline">Ferry {{name}} </span>
              </v-flex>
            </v-layout>
          </v-container>

        <v-card-title>
          <div>
            <h3>{{name}}</h3>
            <div>
              <h4>Arriving at {{ArrivingTerminalName}}</h4>
              <h4>Departed from {{DepartingTerminalName}}</h4>
              <h4>Summary: </h4>
              <p>{{EtaBasis}}</p>
            </div>
            <span class="grey--text">{{id}}</span><br>
            <span>{{latitude}}</span><br>
            <span>{{longitude}}</span>
          </div>
        </v-card-title>
      </v-card>
    </v-flex>
  </v-layout>
</div>
</template>

<script>
export default {
  props: [
    "name",
    "id",
    "latitude",
    "longitude",
    "DepartingTerminalName",
    "ArrivingTerminalName",
    "EtaBasis"
  ]
};
</script>

<style>
</style>
