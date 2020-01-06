<template>
  <v-app class="ms_main_wrapper m-0" id="v_app">
    <!-- navigate -->

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
      <div class="ms_logo_inner">
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
          >
              <a class="d-inline-flex pl-0 pr-0">
                <span class="nav_icon">
                  <span
                    v-bind:class="item.icon"
                    class="d-inline-flex flex-row"
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
    <!-- sidebar -->
    <v-app-bar :clipped-left="clipped" fixed app class="sidebar">
      <v-container fluid class="ma-0 pa-0 fill-height p-md-4">
        <v-row>
          <v-app-bar-nav-icon
            @click.stop="drawer = !drawer"
            class="color_fff"
          />

          <v-btn icon @click.stop="miniVariant = !miniVariant">
            <v-icon class="color_fff"
              >mdi-{{ `chevron-${miniVariant ? "right" : "left"}` }}</v-icon
            >
          </v-btn>
          <v-btn icon @click.stop="clipped = !clipped" class="color_fff">
            <v-icon class="color_fff">mdi-application</v-icon>
          </v-btn>
          <v-spacer />
        </v-row>
      </v-container>
    </v-app-bar>
    <!-- content -->
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <!-- footer -->
    <v-footer :fixed="fixed" app style=" p-0">
      <div class="ms_player_wrapper">
        <div class="ms_player_close">
          <i class="fa fa-angle-up" aria-hidden="true"></i>
        </div>
        <div class="player_mid">
          <div class="audio-player">
            <div id="jquery_jplayer_1" class="jp-jplayer"></div>
            <div
              id="jp_container_1"
              class="jp-audio"
              role="application"
              aria-label="media player"
            >
              <div class="player_left">
                <div class="ms_play_song">
                  <div class="play_song_name">
                    <a href="javascript:void(0);" id="playlist-text">
                      <div class="jp-now-playing flex-item">
                        <div class="jp-track-name"></div>
                        <div class="jp-artist-name"></div>
                      </div>
                    </a>
                  </div>
                </div>
                <div class="play_song_options">
                  <ul>
                    <li>
                      <a href="#"
                        ><span class="song_optn_icon"
                          ><i class="ms_icon icon_download"></i></span
                        >download now</a
                      >
                    </li>
                    <li>
                      <a href="#"
                        ><span class="song_optn_icon"
                          ><i class="ms_icon icon_fav"></i></span
                        >Add To Favourites</a
                      >
                    </li>
                    <li>
                      <a href="#"
                        ><span class="song_optn_icon"
                          ><i class="ms_icon icon_playlist"></i></span
                        >Add To Playlist</a
                      >
                    </li>
                    <li>
                      <a href="#"
                        ><span class="song_optn_icon"
                          ><i class="ms_icon icon_share"></i></span
                        >Share</a
                      >
                    </li>
                  </ul>
                </div>
                <span class="play-left-arrow"
                  ><i class="fa fa-angle-right" aria-hidden="true"></i
                ></span>
              </div>
              <!----Right Queue---->
              <div class="jp_queue_wrapper">
                <span class="que_text" id="myPlaylistQueue"
                  ><i class="fa fa-angle-up" aria-hidden="true"></i> queue</span
                >
                <div id="playlist-wrap" class="jp-playlist">
                  <div class="jp_queue_cls">
                    <i class="fa fa-times" aria-hidden="true"></i>
                  </div>
                  <h2>queue</h2>
                  <div class="jp_queue_list_inner">
                    <ul>
                      <li>&nbsp;</li>
                    </ul>
                  </div>
                  <div class="jp_queue_btn">
                    <a
                      href="javascript:;"
                      class="ms_clear"
                      data-toggle="modal"
                      data-target="#clear_modal"
                      >clear</a
                    >
                    <a
                      href="clear_modal.html"
                      class="ms_save"
                      data-toggle="modal"
                      data-target="#save_modal"
                      >save</a
                    >
                  </div>
                </div>
              </div>
              <div class="jp-type-playlist">
                <div class="jp-gui jp-interface flex-wrap">
                  <div class="jp-controls flex-item">
                    <button class="jp-previous" tabindex="0">
                      <i class="ms_play_control"></i>
                    </button>
                    <button class="jp-play" tabindex="0">
                      <i class="ms_play_control"></i>
                    </button>
                    <button class="jp-next" tabindex="0">
                      <i class="ms_play_control"></i>
                    </button>
                  </div>
                  <div class="jp-progress-container flex-item">
                    <div class="jp-time-holder">
                      <span
                        class="jp-current-time"
                        role="timer"
                        aria-label="time"
                        >&nbsp;</span
                      >
                      <span
                        class="jp-duration"
                        role="timer"
                        aria-label="duration"
                        >&nbsp;</span
                      >
                    </div>
                    <div class="jp-progress">
                      <div class="jp-seek-bar">
                        <div class="jp-play-bar">
                          <div class="bullet"></div>
                        </div>
                      </div>
                    </div>
                  </div>
                  <div class="jp-volume-controls flex-item">
                    <div class="widget knob-container">
                      <div class="knob-wrapper-outer">
                        <div class="knob-wrapper">
                          <div class="knob-mask">
                            <div class="knob d3"><span></span></div>
                            <div class="handle"></div>
                            <div class="round">
                              <img src="images/svg/volume.svg" alt="" />
                            </div>
                          </div>
                        </div>
                        <!-- <input></input> -->
                      </div>
                    </div>
                  </div>
                  <div class="jp-toggles flex-item">
                    <button class="jp-shuffle" tabindex="0" title="Shuffle">
                      <i class="ms_play_control"></i>
                    </button>
                    <button class="jp-repeat" tabindex="0" title="Repeat">
                      <i class="ms_play_control"></i>
                    </button>
                  </div>
                  <div class="jp_quality_optn custom_select">
                    <select>
                      <option>quality</option>
                      <option value="1">HD</option>
                      <option value="2">High</option>
                      <option value="3">medium</option>
                      <option value="4">low</option>
                    </select>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <!--main div-->
      </div>
    </v-footer>
  </v-app>
</template>
<style lang="css">
@import url("~/assets/css/main.css");
@import url("~/assets/css/fonts.css");
@import url("~/assets/css/style.css");
@import url("~/assets/css/font-awesome.min.css");
@import url("~/assets/css/bootstrap.css");
header {
  background-color: #1b2039 !important;
  color: #fff;
}
#nav_css{
  position:fixed;
}
#list_router a:hover,
#list_router a:active {
  background-color: #2cc8e5;
  background-position: 0px 0px;
  color: #ffffff;
}
.color_fff {
  color: #fff !important;
}
.navigate {
  margin: 0;
  color: white !important;
  background: #14182a !important;
  position: fixed;
}
.color {
  font-family: "Josefin Sans", sans-serif !important;
  font-size: 16px;
  font-weight: 400;
  line-height: 24px;
  color: white !important;
}
a:hover {
  text-decoration: none;
}
.sidebar {
  padding: 0px;
  width: 100% - 200px;
  background-color: #1b2039;
  position: fixed;
}
.icon {
  width: 25px;
  height: 25px;
  display: inline-block;
  vertical-align: middle;
  background-image: url("/assets/images/svg/icon.svg");
  background-repeat: no-repeat;
  transition: all 0.3s ease-in-out;
  -webkit-transition: all 0.3s ease-in-out;
  -moz-transition: all 0.3s ease-in-out;
  display: inline-block;
}
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
      title: "Vuetify.js",
      filters: {
        capitalize: function(value) {
          if (!value) return "";
          value = value.toString();
          return value.charAt(0).toUpperCase() + value.slice(1);
        }
      }
    };
  }
};
</script>
