<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
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
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
        <Favorite/>
      </v-container>
    </v-content>
    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light>
              mdi-repeat
            </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-footer
      :fixed="fixed"
      app
    >
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
import Favorite from '../components/Favorite.vue'
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'トゥースツイート',
          to: '/tooth'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'リバースツイート',
          to: '/inspire'
        },
        {
          icon: 'mdi-chart-bubble',
          title:'一つ飛ばしツイート',
          to: '/bug'
        },
        {
          icon: 'mdi-chart-bubble',
          title: '彼ピッピツイート',
          to: '/karepip'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'fizzbuzzツイート',
          to: '/fizbuzz'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'タヌキツイート',
          to: '/tanuki'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'くしゃみツイート',
          to: '/kushami'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: '変なツイートメーカー'
    }
  },
  components: {
    Favorite
  }
}
</script>
