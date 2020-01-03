<template>
  <v-app >
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
      class="navigate"
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title  >{{item.title}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      class="navigate"
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
      <v-btn
        icon
        @click.stop="fixed = !fixed"
      >
        <v-icon>mdi-minus</v-icon>
      </v-btn>
      <v-toolbar-title>{{title||capitalize}}</v-toolbar-title>
      <v-spacer />

    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>

    <v-footer
      :fixed="fixed"
      app
    >
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<style>
  .back{
      background-color : #14182a !important;
  }
  .navigate{
      background-color : #14182a !important;
  }
</style>
<style >
@import "~/assets/css/style.css";
</style>
<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Discover',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Albums',
          to: '/navigate_routing/albums'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Artists',
          to: '/navigate_routing/artists'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Genres',
          to: '/navigate_routing/genres'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Top Tracks',
          to: '/navigate_routing/top_tracks'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Free Music',
          to: '/navigate_routing/free_music'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Stations',
          to: '/navigate_routing/stations'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Downloads',
          to: '/navigate_routing/downloads'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Purchased',
          to: '/navigate_routing/purchased'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Favourites',
          to: '/navigate_routing/favourites'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'History',
          to: '/navigate_routing/history'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Featured Playlist',
          to: '/navigate_routing/featured_playlist'
        },
        {
          icon: 'mdi-chart-bubble',
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
