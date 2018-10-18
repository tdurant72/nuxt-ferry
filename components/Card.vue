<template>
<div>
  <v-layout>
    <v-flex xs12 sm6>
      <v-card>
          <v-container fill-height fluid>
            <v-layout fill-height>
              <v-flex xs12 align-end flexbox>
                <span class="headline">{{name}}</span>
              </v-flex>
            </v-layout>
          </v-container>

        <v-card-title>
          <div>
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
  props:['name', 'id', 'latitude', 'longitude']
}
</script>

<style>

</style>
