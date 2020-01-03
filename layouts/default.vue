<template>
  <v-app dark class="ms_main_wrapper">
    <!-- navigate -->

    <div class="ms_nav_wrapper">
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
      class="navigate ms_sidemenu_wrapper"
      width='200px'
    >
      <v-list>
         <ul>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <li>
              <a >
                  <span class="nav_icon">
                    <span v-bind:class="item.icon"></span>
                  </span>
                  <span id="nav_text" class="color">
                    {{item.title}}
                  </span>
              </a>
          </li>
        </v-list-item>
         </ul>
      </v-list>
    </v-navigation-drawer>
    </div>
    <!-- sidebar -->
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      class="sidebar"
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />

      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
       <v-btn
        icon
        @click.stop="clipped = !clipped"
      >
        <v-icon>mdi-application</v-icon>
      </v-btn>
      <v-spacer />
    </v-app-bar>
    <!-- content -->
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
<!-- footer -->
    <v-footer
      :fixed="fixed"
      app
    >
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>
<style lang="css">
@import url('~/assets/css/main.css');
@import url('~/assets/css/fonts.css');
@import url('~/assets/css/style.css');
@import url('~/assets/css/font-awesome.min.css');
@import url('~/assets/css/bootstrap.css');

.navigate {
    margin: 0;
    color: white !important;
    background: #14182a !important;
}
.color{
   font-family: 'Josefin Sans', sans-serif !important;
    font-size: 16px;
    font-weight: 400;
    line-height: 24px;
    color: white !important;
}
.sidebar{
  padding: 0px;
  width: 100% - 200px;
  background-color: #1b2039;
  position: fixed;
}
.icon{
  width: 25px;
	height: 25px;
	display: inline-block;
	vertical-align: middle;
	background-image: url('/assets/images/svg/icon.svg');
	background-repeat: no-repeat;
	transition: all 0.3s ease-in-out;
	-webkit-transition: all 0.3s ease-in-out;
	-moz-transition: all 0.3s ease-in-out;
	display: inline-block;
}
</style>


<script>
import '@mdi/font/css/materialdesignicons.css';
import '~/assets/images/svg/icon.svg';
import Vue from 'vue'
import Vuetify from 'vuetify/lib'
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'icon icon_discover',
          title: 'Discover',
          to: '/'
        },
        {
          icon: 'icon icon_albums',
          title: 'Albums',
          to: '/navigate_routing/albums'
        },
        {
          icon: 'icon icon_artists',
          title: 'Artists',
          to: '/navigate_routing/artists'
        },
        {
          icon: 'icon icon_genres',
          title: 'Genres',
          to: '/navigate_routing/genres'
        },
        {
          icon: 'icon icon_tracks',
          title: 'Top Tracks',
          to: '/navigate_routing/top_tracks'
        },
        {
          icon: 'icon icon_music',
          title: 'Free Music',
          to: '/navigate_routing/free_music'
        },
        {
          icon: 'icon icon_station',
          title: 'Stations',
          to: '/navigate_routing/stations'
        },
        {
          icon: 'icon icon_download',
          title: 'Downloads',
          to: '/navigate_routing/downloads'
        },
        {
          icon: 'icon icon_purchased',
          title: 'Purchased',
          to: '/navigate_routing/purchased'
        },
        {
          icon: 'icon icon_favourite',
          title: 'Favourites',
          to: '/navigate_routing/favourites'
        },
        {
          icon: 'icon icon_history',
          title: 'History',
          to: '/navigate_routing/history'
        },
        {
          icon: 'icon icon_fe_playlist',
          title: 'Featured Playlist',
          to: '/navigate_routing/featured_playlist'
        },
        {
          icon: 'icon icon_c_playlist',
          title: 'Create Playlist',
          to: '/navigate_routing/create_playlist'
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
      filters: {
      capitalize: function (value) {
        if (!value) return ''
        value = value.toString()
        return value.charAt(0).toUpperCase() + value.slice(1)
      }
    }
    }
  }
}
</script>
