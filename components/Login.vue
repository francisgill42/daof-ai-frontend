<template>
<div>
<h2>Login</h2>
   
<v-form ref="form" class="mt-3">

<v-row>
<v-col cols="12">
<v-text-field v-model="login.email" :value="UpperCase.email" :rules="EmailRules" label="Email"></v-text-field>
</v-col>
<v-col cols="12">
<v-text-field v-model="login.password" :value="UpperCase.password" :rules="PasswordRules" label="Password"></v-text-field>
</v-col>

<v-col cols="12"></v-col>

<v-col>
<v-btn class="primary" to="/" @click="loginUser">Continue</v-btn>
</v-col>
</v-row>

</v-form>
</div>

</template>
<script>

export default {


data () {
return {

    login : { email : '',password : ''},

   
    EmailRules: [ 
        v => !!v || 'This field is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid',
    ],

    PasswordRules: [ 
        v => !!v || 'This field is required',
        // v => /^[A-Z]+[0-9]+[\$\+@\+]$/.test(v) || 'Password must be strong (hint : A-Z)'
    ],


}

},

computed : {
    UpperCase () {
        let d = this.login;

        return [
            d.email = d.email.toUpperCase(),
            d.password = d.password.toUpperCase(),
        ]
    }
},
   
methods: {
    loginUser(){
    console.log(this.login);

    //if(this.$refs.form.validate()){}

    },  

},
}
</script>