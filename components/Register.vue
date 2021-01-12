<template>
<div>
<h2>Introduction</h2>
   
<v-form ref="form" class="mt-3">

<v-row>
<v-col cols="12">
<v-text-field v-model="register.name" :value="UpperCase.name" :rules="NameRules" label="Name (as per CNIC)"></v-text-field>
</v-col>
<v-col cols="6">
<v-text-field v-model="register.email" :value="UpperCase.email" :rules="EmailRules" label="Email"></v-text-field>
</v-col>
<v-col cols="6">
<v-text-field v-model="register.cell" :value="UpperCase.cell" :rules="CellRules" label="Cell"></v-text-field>
</v-col>
<v-col cols="6">
<v-text-field v-model="register.password" :value="UpperCase.password" :rules="PasswordRules" label="Password"></v-text-field>
</v-col>
<v-col cols="6">
<v-text-field v-model="register.confirm_password" :rules="ConfirmPasswordRules" label="Confirm"></v-text-field>
</v-col>

<v-col cols="12">
    <div class="g-recaptcha" data-sitekey="6LeZeykaAAAAAILTse8_kZa6-PSKvC7NFaZuOa7l"></div>
</v-col>

<v-col>
<v-btn class="primary" to="/login" @click="registerUser">Continue</v-btn>
</v-col>
</v-row>

</v-form>
</div>

</template>
<script>

export default {


data () {
return {

    register : {
        name : '',

        email : '',

        cell : '',

        password : '',

        confirm_password : '',
    },

    e1: 0,

    NameRules: [ 
        v => !!v || 'This field is required',
        v => /^[a-zA-Z]+$/.test(v) || 'This field must be contains aplhabets', 
        v => v.length < 25 || 'Name must be less than 25 characters',
    ],

    CellRules: [
        v => !!v || 'This field is required',  
        v => /^\d+$/.test(v) || 'Must be a number',
        v => (v.length <= 15) || 'Cell must be less than or equal to 15 characters',
    ],

    EmailRules: [ 
        v => !!v || 'This field is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid',
    ],

    PasswordRules: [ 
        v => !!v || 'This field is required',
        // v => /^[A-Z]+[0-9]+[\$\+@\+]$/.test(v) || 'Password must be strong (hint : A-Z)'
    ],

    ConfirmPasswordRules: [ 
        v => !!v || 'This field is required',
        v => v == this.register.password || 'Password field does not matched',
    ],

}

},

computed : {
    UpperCase () {
        let d = this.register;

        return [
            d.name = d.name.toUpperCase(),
            d.email = d.email.toUpperCase(),
            d.password = d.password.toUpperCase(),
        ]
    }
},
   
methods: {



registerUser(){


console.log(this.register);

//if(this.$refs.form.validate()){}

},  

},
}
</script>