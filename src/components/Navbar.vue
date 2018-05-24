<template>

<div class="navbar">

    <v-card>
        <v-list two-line>
          <template v-for="(item, index) in items">
            <v-subheader
              v-if="item.header"
              :key="item.header"
              inset
            >
              {{ item.header }}
            </v-subheader>
            <v-divider
              v-else-if="item.divider"
              :key="index"
              inset
            ></v-divider>
            <v-list-tile
              v-else
              :key="item.title"
              avatar
              ripple
              @click=""
            >
              <v-list-tile-avatar>
                <img :src="item.avatar">
              </v-list-tile-avatar>
              <v-list-tile-content>
                <v-list-tile-title v-html="item.title"></v-list-tile-title>
                <v-list-tile-sub-title v-html="item.subtitle"></v-list-tile-sub-title>
              </v-list-tile-content>
            </v-list-tile>
          </template>
        </v-list>
      </v-card>

      <v-card>
        <v-list two-line>
          <v-list-tile @click="">
            <v-list-tile-action>
              <v-icon>phone</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>(+354) 7727806</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
          <v-divider inset></v-divider>
          <v-list-tile @click="">
            <v-list-tile-action>
              <v-icon>mail</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>Contact Me</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
          <v-divider inset></v-divider>
          <v-list-tile @click="">
            <v-list-tile-action>
              <v-icon>location_on</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>Iceland</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-card>

</div><!-- .navbar -->

</template>


<script>
export default {

    data () {
    return {
     avatar: "./static/avatar.jpg",
     avname: 'My List',
items: [
          { divider: true },
          {
            avatar: './static/avatar.jpg',
            title: 'Óðinn',
            subtitle:
              "<span class='text--primary'>Wp / Vue</span> Developer"
          },
          {
            header: 'Playlists'
          },
          { divider: true },
          {
            avatar: './static/avatar.jpg',
            title: 'Óðinn',
            subtitle:
              "<span class='text--primary'>Tv Shows</span>"
          },
          {
            avatar: 'https://picsum.photos/250/300?image=146',
            title: 'Litla',
            subtitle:
              "<span class='text--primary'>Movies</span>"
          },
        ],

        }
    }
}
</script>