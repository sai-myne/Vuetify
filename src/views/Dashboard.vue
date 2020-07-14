<template>
  <div class="dashboard">
    <h1 class='subtitle-1 grey--text mx-4 mb-4'>Dashboard</h1>
    
    <v-container class="my-5">
        
      <v-card flat class="pa3">
        <v-layout row wrap class="mx-4">
          <v-flex xs12 md6>
            <div class="caption grey--text">Project Title</div>
            <div>Create a new website</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Person</div>
            <div>The Net Ninja</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Due by</div>
            <div>1st Jan 2019</div>
          </v-flex>
          <v-flex xs2 sm4 md2>
            <div class="caption grey--text">Status</div>
            <div>ongoing</div>
          </v-flex>
        </v-layout>
      </v-card>

    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  data(){
    return {
      
    }
  }
}
</script>
