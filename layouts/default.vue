<template>
  <v-app class="ms_main_wrapper m-0" id="v_app">
    <!-- navigate -->
    <template>
      <v-navigation-drawer
        v-model="drawer"
        :mini-variant="miniVariant"
        :clipped="clipped"
        :fixed="fixed"
        app
        class="navigate ms_nav_wrapper p-0 m-0"
        width="200px"
        id="nav_css"
      >
        <div class="ms_logo_inner mb-2">
          <div class="ms_logo">
            <a href="index-2.html"
              ><img src="~/assets/images/logo.png" alt="" class="img-fluid"
            /></a>
          </div>
          <div class="ms_logo_open">
            <a href="index-2.html"
              ><img src="~/assets/images/open_logo.png" alt="" class="img-fluid"
            /></a>
          </div>
        </div>

        <v-list class="m-0 p-0">
          <ul class="p-0" id="list_router">
            <v-list-item
              v-for="(item, i) in items"
              :key="i"
              :to="item.to"
              router
              exact
              class="p-0"
            >
              <a
                class="d-inline-flex pl-3 pr-0 pb-3 m-0 height: 100vh a_control"
              >
                <span class="nav_icon pl-2">
                  <span
                    v-bind:class="item.icon"
                    class="d-inline-flex flex-row color_fff "
                  ></span>
                </span>
                <span id="text" class="color pl-3">
                  {{ item.title }}
                </span>
              </a>
            </v-list-item>
          </ul>
        </v-list>
      </v-navigation-drawer>
    </template>
    <!-- sidebar -->
    <v-app-bar :clipped-left="clipped" fixed app class="sidebar">
      <v-container fluid class="ma-0 pa-0 fill-height p-md-4 px-0">
        <v-layout row class="d-inline-flex">
          <v-flex md1 xs1 class="">
            <v-app-bar-nav-icon
            @click.stop="drawer = !drawer"
            class="color_fff mr-2 justify-center"
          />
          </v-flex>
          <v-flex md5 xs5 class="pt-2">
            <div class="search_header">
              <input
                type="text"
                class="form-control"
                placeholder="Search Music Here.."
              />
              <span class="search_icon">
                <img src="~/assets/images/svg/search.svg" alt="" />
              </span>
            </div>
          </v-flex>
          <v-flex md4 xs3 class="pt-2 d-flex flex-row-reverse">
            <div class="ms_top_right">
              <div class="ms_top_lang">
                <span data-toggle="modal" data-target="#lang_modal"
                  >languages <img src="~/assets/images/svg/lang.svg" alt=""
                /></span>
              </div>
              <div class="ms_top_btn">
                <a
                  href="javascript:;"
                  class="ms_btn reg_btn"
                  data-toggle="modal"
                  data-target="#myModal"
                  ><span>register</span></a
                >
                <a
                  href="javascript:;"
                  class="ms_btn login_btn"
                  data-toggle="modal"
                  data-target="#myModal1"
                  ><span>login</span></a
                >
              </div>
            </div>
          </v-flex>
        </v-layout>
      </v-container>
    </v-app-bar>
    <!-- <v-spacer /> -->
    <!-- content -->
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <!-- footer -->
  </v-app>
</template>
<style lang="css">
@import url("~/assets/css/fonts.css");
@import url("~/assets/css/font-awesome.min.css");
@import url("~/assets/css/bootstrap.css");
@import url("~/assets/css/style.css");
@import url("~/assets/css/main.css");
</style>

<script>
import "@mdi/font/css/materialdesignicons.css";
import "~/assets/images/svg/icon.svg";
import Vue from "vue";
import Vuetify from "vuetify/lib";
export default {
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
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Vuetify.js"
    };
  }
};
</script>
