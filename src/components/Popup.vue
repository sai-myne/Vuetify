<template>
    <v-dialog max-width="600px">
        <template v-slot:activator="{on}">
            <v-btn text class="success" v-on="on">Add new project</v-btn>
        </template>        
        <v-card>
            <v-card-title>
                <h2>Add a New project</h2>
            </v-card-title>
            <v-card-text>
                <v-form class="px-3" ref="form">
                    <v-text-field label="Title" v-model="title" prepend-icon="mdi-folder" :rules="inputRules"></v-text-field>
                    <v-textarea label="Information" v-model="content" prepend-icon="mdi-pencil" :rules="inputRules"></v-textarea>
                    <v-menu>
                        <template v-slot:activator="{on}">
                            <v-text-field :value="formattedDate" v-on="on" label="Due date" prepend-icon="mdi-calendar-range" :rules="inputRules"></v-text-field>
                        </template>
                        <v-date-picker v-model="due"></v-date-picker>
                    </v-menu>
                    <v-spacer></v-spacer>
                    <v-btn text class="success mx-0 mt-3" @click="submit">Add project</v-btn>
                </v-form>
            </v-card-text>
        </v-card>
    </v-dialog>
</template>

<script>
import format from 'date-fns/format'
import parseISO from 'date-fns/parseISO'
import db from '@/fb'

export default {
    data(){
        return{
            title: "",
            content: "",
            due: null,
            inputRules: [
                v => v.length >= 3 || 'Minimum length is 3 characters'
            ]
        }
    },
    methods: {
        submit(){
            if(this.$refs.form.validate()){
                const project = {
                    title: this.title,
                    content: this.content,
                    due: format(parseISO(this.due), 'do MMM yyyy'),
                    person: "The Net Ninja",
                    status: "ongoing"
                }
                db.collection('projects').add(project).then(() => {
                    console.log('Added to database')
                })
            }            
        }
    },
    computed: {
        formattedDate(){
            return this.due ? format(parseISO(this.due), 'do MMM yyyy') : ''
        }
    }
}
</script>