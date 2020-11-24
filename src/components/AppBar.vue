<template>
    <v-layout justify-center>
      <v-app-bar
        color="red darken-4"
        app
        flat
      >
        <v-app-bar-nav-icon color="#fff" @click.stop="drawer = !drawer" class="hidden-md-and-up"></v-app-bar-nav-icon>
        <div
            :class="{'display-5 font-weight-medium': $vuetify.breakpoint.smAndUp,'title font-weight-medium': $vuetify.breakpoint.smAndDown, }"
          ><span class="white--text">JKT48</span></div>
        <v-spacer></v-spacer>
          <v-toolbar-items class="text-right hidden-sm-and-down" id="menu">
            <v-btn
              text
            ><router-link to="/"><span class="white--text text-decoration-none">Home</span></router-link></v-btn>
            <v-btn
              text
            ><router-link to="/about"><span class="white--text">Schedule</span></router-link></v-btn>
            <v-btn
              text
            ><router-link to="/video"><span class="white--text">Member</span></router-link></v-btn>
            <v-btn text>
              <router-link to="/photo"><span class="white--text">Shop</span></router-link>
            </v-btn>
          </v-toolbar-items>
            <v-avatar class="" color="white" size="36">
              <span class="black--text">CJ</span>
            </v-avatar>
      </v-app-bar>
      <v-navigation-drawer
        v-model="drawer"
        absolute
        temporary
        >
        <v-list dense>
            <v-list-item
                v-for="item in items"
                :key="item.title"
                :to="item.link"
                >
                <v-list-item-icon>
                    <v-icon>{{ item.icon }}</v-icon>
                </v-list-item-icon>
                <v-list-item-content>
                    <v-list-item-title>{{ item.title }}</v-list-item-title>
                </v-list-item-content>
            </v-list-item>
        </v-list>
        </v-navigation-drawer>
    </v-layout>
</template>

<script>
export default {
  name: 'AppBar',
  data () {
      return {
        drawer: false,
        items: [
          { title: 'Home', icon: 'mdi-home-variant-outline', link:'/' },
          { title: 'Schedule', icon: 'mdi-account-outline', link:'/s'  },
          { title: 'Member', icon: 'mdi-video-outline', link:'/m'  },
          { title: 'Shop', icon: 'mdi-image-outline', link:'/sh'},
        ],
        options: {
          fitToSection: false,
        }
      }
    },
};
</script>

<style scoped>
  a {  
    text-decoration: none;
    color: black;
    background-color: transparent;
  }
  .atas {
    border-top-left-radius: 20px;
    border-top-right-radius: 20px;
  }
</style>