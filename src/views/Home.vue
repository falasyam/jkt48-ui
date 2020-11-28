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
          src: 'https://jkt48.com/images/banner.home.peek-a-boo-id.jpg',
        },
        {
          src: 'https://jkt48.com/images/banner.home.fly-team-t.jpg',
        },
        {
          src: 'https://jkt48.com/images/banner.home.rapsodi.jpg',
        }
      ],
      model: null,
      member: [
        { name: 'Adriani Elisabeth', src: 'https://jkt48.com/profile/adriani_elizabeth_s.jpg?r=20170308', link: 'jkt48.com'},
        { name: 'Amanina Afiqah', src: 'https://jkt48.com/profile/amanina_afiqah_s.jpg?r=20170308'},
        { name: 'Anindhita Rahma Cahyadi', src: 'https://jkt48.com/profile/aninditha_rahma_cahyadi2_s.jpg?r=20170308'},
        { name: 'Ariella Chalista Ichwan', src: 'https://jkt48.com/profile/ariel_s.jpg?r=20170308'},
        { name: 'Azizi Asadel', src: 'https://jkt48.com/profile/azizi_asadel_s.jpg?r=20170308'},
        { name: 'Cindy Hapsari', src: 'https://jkt48.com/profile/cindy_hapsari_s.jpg?r=20170308'},
        { name: 'Diani Amalia Ramadhani', src: 'https://jkt48.com/profile/diani_s.jpg?r=20170308'},
        { name: 'Eve Antoinette Ichwan', src: 'https://jkt48.com/profile/eve_antoinette_s.jpg?r=20170308'},
        { name: 'Feni Fitriyanti', src: 'https://jkt48.com/profile/feni_fitriyanti_s.jpg?r=20170308'},
        { name: 'Fransisca Saraswati Puspa Dewi', src: 'https://jkt48.com/profile/fransisca_saraswati_puspa_dewi_s.jpg?r=20170308'},
        { name: 'Frieska Anastasia Laksani', src: 'https://jkt48.com/profile/frieska_anastasia_laksani_s.jpg?r=20170308'},
        { name: 'Gabriel Angelina', src: 'https://jkt48.com/profile/gabriel_angelina_s.jpg?r=20170308'},
        { name: 'Gabriella Margareth Warouw', src: 'https://jkt48.com/profile/gabriella_s.jpg?r=20170308'},
        { name: 'Nabila Fitriana', src: 'https://jkt48.com/profile/nabila_fitriana_s.jpg?r=20170308'},
        { name: 'Nadila Cindi Wantari', src: 'https://jkt48.com/profile/nadila_cindi_wantari_s.jpg?r=20170308'},
        { name: 'Ni Made Ayu Vania Aurellia', src: 'https://jkt48.com/profile/made_ayu_vania_aurellia_s.jpg?r=20170308'},
        { name: 'Riska Amelia Putri', src: 'https://jkt48.com/profile/riska_amelia_putri_s.jpg?r=20170308'},
        { name: 'Rona Ariesta Anggraeni', src: 'https://jkt48.com/profile/rona_ariesta_anggraeni_s.jpg?r=20170308'},
        { name: 'Sania Julia', src: 'https://jkt48.com/profile/sania_julia_s.jpg?r=20170308'},
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
