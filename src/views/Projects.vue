<template>
 <div class="projects">
  <span class="subheading grey--text">Projects</span>


  <v-container class="my-5">
      <v-expansion-panels focusable>
    <v-expansion-panel v-for="(item, i) in projects" :key="i">
      <v-expansion-panel-header>{{ item.title }}</v-expansion-panel-header>
      <v-expansion-panel-content>
          <div class="caption grey--text">{{ item.duedate }}</div>
          <div class="body-2 subheading">{{ item.content }}</div>        
      </v-expansion-panel-content>
    </v-expansion-panel>
  </v-expansion-panels>
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
  }

}
</script>