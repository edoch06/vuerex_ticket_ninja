<template>
 <div class="dashboard">
   <span class="subheading grey--text">Dashboard</span>
   <v-container class="my-5">

     <v-layout row wrap mb-3>
       <v-tooltip small top>
        <template v-slot:activator="{ on }">
       <v-btn small depressed color="grey lighten-4" @click="sortBy('title')" v-on="on">
         <v-icon left class="grey--text">folder</v-icon>
         <span class="caption text-lowercase grey--text">by project name</span>
       </v-btn>
        </template>
          <span class="caption">Sort project by project name</span>
        </v-tooltip>
        
        <v-tooltip small top>
        <template v-slot:activator="{ on }">
       <v-btn small depressed color="grey lighten-4" @click="sortBy('person')"  v-on="on">
        <v-icon left class="grey--text">person</v-icon>
         <span class="caption text-lowercase grey--text">by person</span>
       </v-btn>
        </template>
          <span class="caption">Sort project by person</span>
        </v-tooltip>


     </v-layout>
     
     <v-card flat tile class="px-5 py-1"  v-for="(item, i) in projects" :key="i">
     <v-layout row wrap :class="`pa-3 project ${item.status}`">
       <v-flex xs12 md6>
         <div class="caption grey--text"> Project Title</div>
         <div v-text="item.title"></div>
       </v-flex> 
        <v-flex xs6 sm4 md2>
         <div class="caption grey--text"> Project Title</div>
         <div v-text="item.person"></div>
       </v-flex> 
       <v-flex xs6 sm4 md2>
         <div class="caption grey--text"> Due Date</div>
         <div v-text="item.duedate"></div>
       </v-flex> 
       <v-flex xs2 sm4 md2>
          <div class="text-right">
            <v-chip small :class="`chip ${item.status} white--text my-2 caption`">{{ item.status }}</v-chip>           
          </div>         
       </v-flex>      
     </v-layout>
      <v-divider></v-divider>
     </v-card>
    

  
   </v-container>
 </div>
</template>

<script>
// @ is an alias to /src


export default {
 
data () {
  return {
       item: 0,
      projects: [
        { title: 'Design website', person : 'The Ninja' , duedate: '1st Jan 2014', status : 'ongoing',content : 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ab atque adipisci similique obcaecati odio maxime placeat eligendi laboriosam, fuga, quas assumenda quibusdam nulla dicta numquam nam necessitatibus labore. Incidunt, cum!'}, 
        { title: 'Make a video', person : 'Ryu' , duedate: '2nd Feb 2016', status : 'completed', content : 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolores possimus porro numquam iste deleniti veritatis tempora totam blanditiis. Ipsam, rerum sequi? Eius fuga, explicabo quasi dignissimos tempore rerum. Necessitatibus, neque?' },
        {title: 'Skectch an academic writing', person : 'Jane' , duedate: '10th Feb 2017', status : 'ongoing' ,content : 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Consectetur distinctio sint dolor! Enim veniam numquam vero eius neque voluptate tenetur voluptas. Reiciendis nihil voluptatum ipsa iure amet inventore officia. Amet?'},
        {title: 'Draw a project flow', person : 'Peter' , duedate: '13th Feb 2017', status : 'overdue' ,content : 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Voluptatum vel eveniet quos vero nihil sed, asperiores doloribus ad sunt laudantium minus cumque nobis quae, ducimus necessitatibus maxime magni voluptate rerum?'},
      ],
  }
},
methods: {
    sortBy(prop) {
      this.projects.sort((a,b) => a[prop] < b[prop] ? -1 : 1)
    }
  }

}
</script>


<style scoped>


.project.completed {
  border-left: 4px solid  #0099ff;
}
.project.ongoing {
  border-left: 4px solid #ffa64d;
}
.project.overdue {
  border-left: 4px solid #ff1a8c;
}

.chip.completed{
  background: #3cd1c2;
}
.chip.ongoing{
  background: #ffaa2c;
}
.chip.overdue{
  background: #f83e70;
}

</style>
