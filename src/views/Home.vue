<template>
  <section>
    <AppBar/>
       <v-responsive>
          <v-carousel cycle :show-arrows="false" hide-delimiters style="width:100%; ">
            <v-carousel-item
              v-for="(item,i) in items"
              :key="i"
              :src="item.src"
            ></v-carousel-item>
          </v-carousel>
        </v-responsive>
    <v-container>
      <div class="py-6"></div>
      <span class="red--text font-weight-black headline">News</span>
      <div class="py-2"></div>
      <v-tabs fixed-tabs color="red darken-4">
        <v-tab>All</v-tab>
        <v-tab>Theater</v-tab>
        <v-tab>Event</v-tab>
        <v-tab>Release</v-tab>
        <v-tab>Other</v-tab>
      </v-tabs>
      <div class="py-3"></div>
      <v-card outlined>
        <v-card-text>
          <span class="font-weight-bold">24 Juni 2020</span><br/>
          <div class="py-1"></div>
          <span class="font-weight-medium pink white--text">Theater</span><br/>
          <div class="py-2"></div>
          <span class="headline red--text text-decoration-none"><a href="#" class="text-decoration-none">2nd Live Streaming "Back To Theater ~First Step is Unit Song!~"</a></span>
          <div class="py-3"></div>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn depressed color="red">
            <span class="white--text">READ MORE</span>
          </v-btn>
        </v-card-actions>
      </v-card>
      <div class="py-3"></div>
    </v-container>
    <v-layout justify-center>
      <v-btn outlined color="red">Load More</v-btn>
      <div class="py-3"></div>
    </v-layout>
    <v-container>
      <div class="py-6"></div>
      <span class="red--text font-weight-black headline">Member</span>
      <div class="py-2"></div>
      <v-tabs fixed-tabs color="red darken-4">
        <v-tab>Team J</v-tab>
        <v-tab>Team KIII</v-tab>
        <v-tab>Team T</v-tab>
      </v-tabs>
      <div class="py-3"></div>
    </v-container>
  </section>
</template>

<script>
// @ is an alias to /src
import AppBar from '../components/AppBar'

export default {
  name: 'Home',
  components: {
    AppBar,
  },
  data () {
    return {
      items: [
        {
          src: 'https://jkt48.com/images/banner.home.peek-a-boo-id.jpg',
        },
        {
          src: 'https://jkt48.com/images/banner.home.fly-team-t.jpg',
        },
        {
          src: 'https://jkt48.com/images/banner.home.rapsodi.jpg',
        }
      ],
    }
  },
}
</script>
