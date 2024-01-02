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
        <v-tab>Member</v-tab>
        <v-tab>Trainee</v-tab>
      </v-tabs>
      <div class="py-3"></div>
        <v-slide-group
          v-model="model"
          class=""
          mandatory
          show-arrows="hide-md-and-up"
        >
          <v-slide-item
            v-for="member in member"
            :key="member.name"
            v-slot:default="{ active, toggle}"
          >
            <v-card
              :color="active ? 'red darken-4' : 'grey lighten-1'"
              class="ma-4"
              height="141"
              width="100"
              @click="toggle"
            >
              <v-img :src="member.src">
              </v-img>
              <v-row
                class="fill-height"
                align="center"
                justify="center"
              >
                <v-scale-transition>
                  <v-card-title
                    v-if="active"
                    v-text="member.name"
                  ></v-card-title>
                </v-scale-transition>
              </v-row>
            </v-card>
          </v-slide-item>
        </v-slide-group>
        <div class="py-3"></div>
    </v-container>
    <v-layout justify-center>
      <v-btn outlined color="red">Load More</v-btn>
      <div class="py-3"></div>
    </v-layout>
    <div class="py-5"></div>
    <v-footer
      color="red darken-4"
      padless
    >
      <v-row
        justify="center"
        no-gutters
      >
        <v-btn
          v-for="link in links"
          :key="link"
          color="white"
          text
          rounded
          class="my-2"
        >
          {{ link }}
        </v-btn>
        <v-col
          class="red darken-4 py-4 text-center white--text"
          cols="12"
        >
          {{ new Date().getFullYear() }} — <strong>JKT48 Operation Team</strong>
        </v-col>
      </v-row>
    </v-footer>
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
          src: 'https://jkt48.com/images/banner.home.flowerfulpb-id.jpg',
        },
        {
          src: 'https://jkt48.com/images/banner.home.jkt48v.jpg',
        },
        {
          src: 'https://jkt48.com/images/banner.home.tokopedia.jpg',
        }
      ],
      model: null,
      member: [
        { name: 'Adzana Shaliha', src: 'https://jkt48.com/profile/adzana_shaliha.jpg?v=20230116', link: 'jkt48.com'},
        { name: 'Amanda Sukma', src: 'https://jkt48.com/profile/amanda_sukma.jpg?v=20230530'},
        { name: 'Angelina Christy', src: 'https://jkt48.com/profile/angelina_christy.jpg?v=20230116'},
        { name: 'Aurellia', src: 'https://jkt48.com/profile/aurellia.jpg?v=20230531'},
        { name: 'Azizi Asadel', src: 'https://jkt48.com/profile/azizi_asadel.jpg?v=20230116'},
        { name: 'Callista Alifia', src: 'https://jkt48.com/profile/callista_alifia.jpg?v=20230531'},
        { name: 'Cornelia Vanisa', src: 'https://jkt48.com/profile/cornelia_vanisa.jpg?v=20230116'},
        { name: 'Febriola Sinambela', src: 'https://jkt48.com/profile/febriola_sinambela.jpg?v=20230116'},
        { name: 'Feni Fitriyanti', src: 'https://jkt48.com/profile/feni_fitriyanti.jpg?v=20230116'},
        { name: 'Fiony Alveria', src: 'https://jkt48.com/profile/fiony_alveria.jpg?v=20230116'},
        { name: 'Flora Shafiq', src: 'https://jkt48.com/profile/flora_shafiq.jpg?v=20230116'},
        { name: 'Freya Jayawardana', src: 'https://jkt48.com/profile/freya_jayawardana.jpg?v=20230116'},
        { name: 'Gabriela Abigail', src: 'https://jkt48.com/profile/gabriela_abigail.jpg?v=20230531'},
        { name: 'Gita Sekar Andarini', src: 'https://jkt48.com/profile/gita_sekar_andarini.jpg?v=20230116'},
        ],
      links: [
        'Home',
        'News',
        'Member',
        'About JKT48',
        'Produser',
        'Kontak',
      ],
    }
  },
}
</script>
