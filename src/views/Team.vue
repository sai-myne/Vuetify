<template>
  <div class="team">
    <h1 class='subtitle-1 grey--text mx-4 mb-4'>Team</h1>

    <v-container class="my-5">
        <v-layout row wrap>
            <v-flex xs12 sm6 md4 lg3 v-for="person in team" :key="person.name">
                <v-card flat class="text-center ma-3">
                    <v-responsive class="pt-4">
                        Image gose here
                    </v-responsive>
                    <v-card-text>
                        <div class="subtitle-1">{{ person.name }}</div>
                        <div class="grey--text">{{ person.role }}</div>
                    </v-card-text>
                    <v-card-actions>
                        <v-btn text color="grey">
                            <v-icon small left>mdi-message</v-icon>
                            <span>Message</span>
                        </v-btn>
                    </v-card-actions>
                </v-card>
            </v-flex>
        </v-layout>
    </v-container>
    
  </div>
</template>

<script>
// @ is an alias to /src

export default {
    data(){
        return{
            team: [
                { name: 'The Net Ninja', role: 'Web developer' },
                { name: 'Ryu', role: 'Graphic designer' },
                { name: 'Chun Li', role: 'Web developer' },
                { name: 'Gouken', role: 'Social media maverick' },
                { name: 'Yoshi', role: 'Sales guru'}
            ]
        }
    }
}
</script>
