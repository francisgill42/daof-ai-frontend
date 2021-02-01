<template>

<v-card>

 
      
    <v-stepper v-model="e1">
    <v-stepper-header>

      <v-stepper-step
      color="primary"
        :complete="e1 > 1"
        step="1"
      >
        Customer Information
      </v-stepper-step>

      <v-divider></v-divider>

      <v-stepper-step
      color="primary"
        :complete="e1 > 2"
        step="2"
      >
        Investment Details
      </v-stepper-step>

       <v-divider></v-divider>

       <v-stepper-step
      color="primary"
        :complete="e1 > 3"
        step="3"
      >
        Documentations
      </v-stepper-step>

       <v-divider></v-divider>

       <v-stepper-step
      color="primary"
        :complete="e1 > 4"
        step="4"
      >
        Declaration
      </v-stepper-step>

    
    </v-stepper-header>

    <v-stepper-items>

      <v-stepper-content step="1">
          <First class="mt-10"/> 
          <v-btn class="primary" @click="e1 = 2">submit</v-btn>
      </v-stepper-content>

      <v-stepper-content step="2">
          <Second class="mt-10"/> 
          <v-btn class="primary" @click="e1 = 5">submit</v-btn>
      </v-stepper-content>

       <v-stepper-content step="3">
          <Third class="mt-10"/> 
          <v-btn class="primary" @click="e1 = 4">submit</v-btn>
      </v-stepper-content>

      <v-stepper-content step="4">
          <Four class="mt-10"/> 
          <v-btn class="primary" @click="e1 = 4">submit</v-btn>
      </v-stepper-content>

        <v-stepper-content step="5">
          <Fifth class="mt-10"/> 
          <v-btn class="primary" @click="e1 = 5">submit</v-btn>
       </v-stepper-content>

    </v-stepper-items>
  </v-stepper>
</v-card>

</template>

<script>
import Register from '~/components/Register'
import First from '~/components/First'
import Second from '~/components/Second'
import Fifth from '~/components/Fifth'

export default {

  layout : 'web',

  data () {
    return {
      e1:1
    }
  },

  components : {
  
    Register,
    First,
    Second,
    Fifth
  }
  
}
</script>