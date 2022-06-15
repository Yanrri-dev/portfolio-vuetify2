<template>
   <div>  
     <v-app-bar
      app
      color="purple darken-4"
      dark
    >
      <!-- <div class="d-flex align-center" start>
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div> -->
      
      <v-app-bar-nav-icon class="d-flex d-sm-none" @click.stop="drawer = !drawer">
        
      </v-app-bar-nav-icon>
      <!-- <v-row justify="center" no-gutters color="primary" dark>
        <v-tabs centered>
            <v-tab to="/">Home</v-tab>
            <v-tab to="/about">About Me</v-tab>
            <v-tab to="/projects">Projects</v-tab>
            <v-tab to="/contact">Contact</v-tab>
        </v-tabs>
      </v-row> -->
      
        <v-tabs
            class="d-none d-sm-flex justify-center"
            background-color="purple darken-4"
            centered
            dark
        >
        <v-tabs-slider></v-tabs-slider>
            <v-tab to="/">Home</v-tab>
            <v-tab to="/about">About Me</v-tab>
            <v-tab to="/projects">Projects</v-tab>
            <v-tab to="/contact">Contact</v-tab>
        </v-tabs>


      <v-spacer></v-spacer>

      <v-btn icon v-if="!$vuetify.theme.dark" @click="$vuetify.theme.dark = ! $vuetify.theme.dark">
        <v-icon class="mr-1" color="white darken-4">mdi-brightness-4</v-icon>
      </v-btn>
      <v-btn icon v-else-if="$vuetify.theme.dark" @click="$vuetify.theme.dark = ! $vuetify.theme.dark">
        <v-icon color="yellow darken-3">mdi-white-balance-sunny</v-icon>
      </v-btn>
    
    </v-app-bar>
    
    <v-navigation-drawer
      v-model="drawer"
      absolute
      top
      temporary
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item to="/">
            <v-list-item-title>Home</v-list-item-title>
          </v-list-item>

          <v-list-item to="/about">
            <v-list-item-title>About Me</v-list-item-title>
          </v-list-item>

          <v-list-item to="/projects">
            <v-list-item-title>Projects</v-list-item-title>
          </v-list-item>

          <v-list-item to="/contact">
            <v-list-item-title>Contact</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    </div> 
    
</template>

<script>
export default {
    name:"Navbar",
    data: () => ({
      drawer: false,
      group: null,
    }),

    watch: {
      group () {
        this.drawer = false
      },
    },
}
</script>