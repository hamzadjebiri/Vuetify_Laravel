


<template>
   
   <v-app >

         
                  
             
        <v-jumbotron  >
         
        <v-layout align-center>
          <v-flex>
            <h3 class="display-3">Welcome to the site</h3>
  
            <span class="subheading">Lorem ipsum dolor sit amet, pri veniam forensibus id. Vis maluisset molestiae id, ad semper lobortis cum. At impetus detraxit incorrupte usu, repudiare assueverit ex eum, ne nam essent vocent admodum.</span>
  
            <v-divider class="my-3"></v-divider>
  
            <div class="title mb-3">Check out our newest features!</div>
  
            <v-btn
              class="mx-0"
              color="primary"
              large
            >
              See more
            </v-btn>
          </v-flex>
        </v-layout>
      </v-container>
        
       </v-jumbotron>
          
        <!-- ***** ***** ***** ***** *****  CHILDS :  ***** ***** ***** ***** ***** -->


               



         

   </v-app>
    
</template>


<script>
export default {
    
    data(){

         return {

              items: ['Foo', 'Bar', 'Fizz', 'Buzz'] ,

              isLoading : false ,

              search :'' , 

              model : ''
   
         }
    }
}
</script>


<style>

   .v-jumbotron{

   }
</style>
