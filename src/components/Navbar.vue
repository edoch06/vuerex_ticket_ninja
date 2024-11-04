<template>
    <nav>
        <v-app-bar app flat class="grey lighten-4">
            <v-app-bar-nav-icon class="grey--text" @click="drawer=!drawer"></v-app-bar-nav-icon>
            <v-toolbar-title class="text-uppercase grey--text">
      <span class="font-weight-light">todo</span>
      <span>ninja</span>
      </v-toolbar-title>
 <v-spacer></v-spacer>
            <v-btn depressed color="grey lighten-4 grey--text"> 
                <span>Sign Out</span>
                <v-icon right>exit_to_app</v-icon>
            </v-btn>
        </v-app-bar>
        <v-navigation-drawer app v-model="drawer" class="primary">
       <v-card  flat class="mx-2 primary" max-width="300" tile>

   
    <v-layout column align-center>
      <v-flex xs1 mt-5>
        <v-avatar size="74" color="white">
          <img src="@/assets/avatar.png" alt="edmond">
        </v-avatar>      
      </v-flex> 
      <v-flex xs1 mt-3>
        <span class="white--text subheading ">Edmond Ochola</span> 
  </v-flex> 
      <v-flex xs1 >
        <span class="white--text caption">edoch06@gmail</span> 
      </v-flex>
      <v-flex >
        <v-divider></v-divider>  
      </v-flex> 
     
    </v-layout>
   
   
    <v-list flat>
      <v-list-item-group v-model="item" class="subheading white--text">
        <v-list-item v-for="(item, i) in items" :key="i" router :to="item.route">
          <v-list-item-icon>
            <v-icon v-text="item.icon"></v-icon>
        </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title v-text="item.text"></v-list-item-title>
        </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-card>
        </v-navigation-drawer>
    </nav>
</template>

<script>
export default {
    data (){
        return {
            drawer : false,
            item: 0,
      items: [
        { text: 'Dashboard', icon: 'dashboard' , route: '/'},
        { text: 'My Projects', icon: 'folder', route: '/projects' },
        { text: 'Team', icon: 'person', route: '/team' },
      ],
        }
    }
}

</script>