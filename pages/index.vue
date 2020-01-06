<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <div class="text-center">
        <logo />
        <vuetify-logo />
      </div>
      <p class="demo">4234234</p>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quasi eaque
        iure voluptatibus. Tenetur fugit earum voluptatem id, omnis non dolorum,
        ipsa commodi libero illo voluptas. Hic facere rerum quasi ipsam?
      </p>
      <span class="icon icon_albums"></span>
      <div class="list_router">

      </div>
    </v-flex>
  </v-layout>
</template>
<style lang="css" scope>
/* @import url("~/assets/css/main.css"); */
/* @import url("~/assets/css/fonts.css"); */
/* @import url("~/assets/css/style.css"); */
/* @import url("~/assets/css/font-awesome.min.css"); */
/* @import url("~/assets/css/bootstrap.css"); */

/* .icon {
  width: 25px;
  height: 25px;
  display: inline-block;
  vertical-align: middle;
  background-image: url(~assets/images/svg/icon.svg);
  background-repeat: no-repeat;
  transition: all 0.3s ease-in-out;
  -webkit-transition: all 0.3s ease-in-out;
  -moz-transition: all 0.3s ease-in-out;
  display: inline-block;
} */
.list_router a:hover,
.list_router a:active {
  background-color: #2cc8e5;
  background-position: 0px 0px;
  color: #ffffff;
}
</style>

<script>
import Logo from "~/components/Logo.vue";
import VuetifyLogo from "~/components/VuetifyLogo.vue";

export default {
  components: {
    Logo,
    VuetifyLogo
  },
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "icon icon_discover",
          title: "Discover",
          to: "/"
        },
        {
          icon: "icon icon_albums",
          title: "Albums",
          to: "/navigate_routing/albums"
        },
        {
          icon: "icon icon_artists",
          title: "Artists",
          to: "/navigate_routing/artists"
        },
        {
          icon: "icon icon_genres",
          title: "Genres",
          to: "/navigate_routing/genres"
        },
        {
          icon: "icon icon_tracks",
          title: "Top Tracks",
          to: "/navigate_routing/top_tracks"
        },
        {
          icon: "icon icon_music",
          title: "Free Music",
          to: "/navigate_routing/free_music"
        },
        {
          icon: "icon icon_station",
          title: "Stations",
          to: "/navigate_routing/stations"
        },
        {
          icon: "icon icon_download",
          title: "Downloads",
          to: "/navigate_routing/downloads"
        },
        {
          icon: "icon icon_purchased",
          title: "Purchased",
          to: "/navigate_routing/purchased"
        },
        {
          icon: "icon icon_favourite",
          title: "Favourites",
          to: "/navigate_routing/favourites"
        },
        {
          icon: "icon icon_history",
          title: "History",
          to: "/navigate_routing/history"
        },
        {
          icon: "icon icon_fe_playlist",
          title: "Featured Playlist",
          to: "/navigate_routing/featured_playlist"
        },
        {
          icon: "icon icon_c_playlist",
          title: "Create Playlist",
          to: "/navigate_routing/create_playlist"
        }
      ]
    };
  }
};
</script>
