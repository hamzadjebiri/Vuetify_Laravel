<template >
     
         <v-navigation-drawer
                     v-model="Drawer"
                     fixed
                     clipped
                     app            
                     
         >

      <v-list dense>
        <v-list-tile v-for="item in items" :key="item.text" @click="">
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title >
              {{ item.text }}
            </v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>


        <v-subheader class="mt-3 grey--text text--darken-1">SUBSCRIPTIONS</v-subheader>
        <v-list>
          <v-list-tile v-for="item in items2" :key="item.text" avatar @click="">
            <v-list-tile-avatar>
              <img :src="`https://randomuser.me/api/portraits/men/${item.picture}.jpg`" alt="">
            </v-list-tile-avatar>
            <v-list-tile-title v-text="item.text"></v-list-tile-title>
          </v-list-tile>
        </v-list>
        <v-list-tile class="mt-3" @click="">
          <v-list-tile-action>
            <v-icon color="grey darken-1">add_circle_outline</v-icon>
          </v-list-tile-action>
          <v-list-tile-title class="grey--text text--darken-1">Browse Channels</v-list-tile-title>
        </v-list-tile>
        <v-list-tile @click="">
          <v-list-tile-action>
            <v-icon color="grey darken-1">settings</v-icon>
          </v-list-tile-action>
          <v-list-tile-title class="grey--text text--darken-1">Manage Subscriptions</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
</template>


<script>
export default {

    props: ['DrawerFromNavbar'] ,

    data() {

         return {

               Drawer : false , 
               
               mini : false ,

               /* Hadouma les items rempalcihoum b nav-links bch ki nsagher lecran iwalou a coté */

               items: [

                     { icon: 'trending_up', text: 'Most Popular' },
                     { icon: 'subscriptions', text: 'Subscriptions' },
                     { icon: 'history', text: 'History' },
                     { icon: 'featured_play_list', text: 'Playlists' },
                     { icon: 'watch_later', text: 'Watch Later' }
                
                 ],

               items2: [
                 { picture: 28, text: 'Joseph' },
                 { picture: 38, text: 'Apple' },
                 { picture: 48, text: 'Xbox Ahoy' },
                 { picture: 58, text: 'Nokia' },
                 { picture: 78, text: 'MKBHD' }
               ]

           }
    },


    watch : {

        // when navbar component (the parent) change DrawerFromNavbar we change Drawer

        DrawerFromNavbar:function(){
            
            if(this.Drawer == true) this.Drawer = false ;

             else this.Drawer = true ;

            console.log(this.Drawer) ;
             
        },

        // then when Drawer changed we send event from child 'navdrawer" To parent "navbar"

        Drawer:function(){

               this.$emit('DrawerHasChangedOnChild',false) ;
        }

       
    },

    methods : {

    }
    
}
</script>
