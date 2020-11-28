<template>
    <v-layout justify-center class="overflow-hidden">
      <v-app-bar
        color="red darken-4"
        app
        flat
      >
        <v-app-bar-nav-icon color="#fff" @click.stop="sheet = !sheet" class="hidden-md-and-up"></v-app-bar-nav-icon>
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
            ><router-link to="/404"><span class="white--text">Schedule</span></router-link></v-btn>
            <v-btn
              text
            ><router-link to="/404"><span class="white--text">Member</span></router-link></v-btn>
            <v-btn text>
              <router-link to="/404"><span class="white--text">Shop</span></router-link>
            </v-btn>
          </v-toolbar-items>
            <v-avatar class="" color="grey lighten-2" size="36">
              <span class="black--text">CJ</span>
            </v-avatar>
      </v-app-bar>
        <v-bottom-sheet v-model="sheet" class="atas">
        <v-list shaped class="atas">
          <v-btn depressed :style="{left: '50%', transform:'translateX(-50%)'}" width="1px" height="4px" color="#d1d1cf"></v-btn>
            <v-list-item>
              <v-list-item-avatar>
                <v-avatar class="" color="grey lighten-2" size="36">
                  <span class="black--text">CJ</span>
                </v-avatar>
              </v-list-item-avatar>
            </v-list-item>
            <v-list-item link>
              <v-list-item-content>
                <v-list-item-title class="title">
                  Carl Johnson
                </v-list-item-title>
                <v-list-item-subtitle>carl@jkt48.com</v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
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
      </v-bottom-sheet>
    </v-layout>
</template>

<script>
export default {
  name: 'AppBar',
  data () {
      return {
        sheet: false,
        items: [
          { title: 'Home', icon: 'mdi-home-variant-outline', link:'/' },
          { title: 'Schedule', icon: 'mdi-calendar-range', link:'/404'  },
          { title: 'Member', icon: 'mdi-account-outline', link:'/404'  },
          { title: 'Shop', icon: 'mdi-shopping-outline', link:'/404'},
        ],
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