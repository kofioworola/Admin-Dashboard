<template>
<v-container>
<v-col class="mx-auto col-6">

<v-card
elevation="1">
<v-col class="text-center">
<v-col
color-primary
class="dispay-1 font-weight-bold deep-purple--text">
    Sign In
</v-col>
<v-col
class="font-weight-bold text">
Login with e-mail address and password</v-col>
</v-col>

<v-col class="px-4">
<v-text-field
v-model="credentials.username" outlined label="Password">

</v-text-field>
<v-text-field 
v-model="credentials.password" outlined label="Password">
    
</v-text-field>
</v-col>

<v-col class="text-center">
<v-btn 
@click="submitHandler()"
class="mb-5 purple darken-4">
Submit
</v-btn>
</v-col>

</v-card>
</v-col>
</v-container>

</template>

<script>
export default {
    data(){
        return{
            name: "johnson",

            credentials: {
                username:"",
                password:"",
            }
        }
    },
    methods: {
        submitHandler(){
            const userDetails = this.credentials
            console.log(userDetails)
        }
    }
}
</script>