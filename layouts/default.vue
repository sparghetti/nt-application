<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
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
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" v-if="showLeftHand" />
      <v-btn
        outlined
        v-if="showRightHand"
        style="color: deepskyblue"
      >
        <v-icon>mdi-chevron-left</v-icon>
      </v-btn>
<!--      <v-btn-->
<!--        icon-->
<!--        @click.stop="miniVariant = !miniVariant"-->
<!--      >-->
<!--        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>-->
<!--      </v-btn>-->
<!--      <v-btn-->
<!--        icon-->
<!--        @click.stop="clipped = !clipped"-->
<!--      >-->
<!--        <v-icon>mdi-application</v-icon>-->
<!--      </v-btn>-->
<!--      <v-btn-->
<!--        icon-->
<!--        @click.stop="fixed = !fixed"-->
<!--      >-->
<!--        <v-icon>mdi-minus</v-icon>-->
<!--      </v-btn>-->
<!--      <v-toolbar-title v-text="title" />-->
      <v-list-item two-line>
        <v-list-item-content>
          <v-list-item-title><u>{{title}}</u></v-list-item-title>
          <v-list-item-subtitle>Code : CS6320100210</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
<!--     <div class="d-flex flex-column">-->
<!--       <template style="font-weight: bold">-->
<!--         -->
<!--       </template>-->
<!--       <br>-->
<!--       Code : CS632010021-->
<!--     </div>-->
<!--      <div style="font-weight: bold">{{title}}</div>-->
<!--      <br>-->
<!--      Code : CS632010021-->
      <v-spacer />
      <v-btn
        outlined
        v-if="showRightHand"
        @click.stop="rightDrawer = !rightDrawer"
        style="color: deepskyblue"
      >
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      :mini-variant="miniVariant"
      :mini-variant-width="100"
      :clipped="clipped"
      style="border-radius: 7px;"
      class="ma-1"
      temporary
      fixed
    >
      <v-list style="margin-top: 0; padding-top: 0;">
        <div style="background-color: lightslategray; color: white;" class="d-flex justify-center py-1 mb-5">
          Menu bar
        </div>
        <div class="d-flex flex-column justify-center">
          <div v-for="(item, i) in items"
                 :key="i"
          class="my-1 mx-2">
            <v-btn icon
                   outlined
                   block
                   @click.prevent="onClickRoute(item.to)"
                   style="border-radius: 12px"
                   x-large>
              <v-icon>{{ item.icon }}</v-icon>
            </v-btn>
          </div>
          <div class="my-1 mx-2">
            <v-btn icon
                   outlined
                   block
                   style="border-radius: 12px"
                   x-large>
              <v-icon>mdi-cogs</v-icon>
            </v-btn>
          </div>
        </div>

<!--        style 2-->
<!--        <div v-for="(item, i) in items"-->
<!--             :key="i"-->
<!--             :to="item.to"-->
<!--             @click.prevent="onClickRoute(item.to)"-->
<!--             style="color: black; border: solid thin; border-radius: 10px; box-shadow: 2px 2px 5px #888; cursor: pointer"-->
<!--             class="d-flex justify-center pa-4 ma-2">-->
<!--          <v-icon>{{ item.icon }}</v-icon>-->
<!--        </div>-->
<!--   end  style 2-->
<!--        style 1-->
<!--        <v-list-item-->
<!--          v-for="(item, i) in items"-->
<!--          :key="i"-->
<!--          :to="item.to"-->
<!--          router-->
<!--          exact-->
<!--        >-->
<!--          <v-list-item-action>-->
<!--            <v-icon>{{ item.icon }}</v-icon>-->
<!--          </v-list-item-action>-->
<!--          <v-list-item-content>-->
<!--            <v-list-item-title v-text="item.title" />-->
<!--          </v-list-item-content>-->
<!--        </v-list-item>-->
<!--   end  style 1-->
      </v-list>
    </v-navigation-drawer>
    <bottom-navigation style="bottom: 0"></bottom-navigation>
<!--    <v-footer-->
<!--      :absolute="!fixed"-->
<!--      app-->
<!--    >-->
<!--&lt;!&ndash;      <span>&copy; {{ new Date().getFullYear() }}</span>&ndash;&gt;-->
<!--      <template>-->
<!--        <bottom-navigation></bottom-navigation>-->
<!--      </template>-->
<!--    </v-footer>-->
  </v-app>
</template>

<script>
import BottomNavigation from '@/components/BottomNavigation'
export default {
  name: 'DefaultLayout',
  components: {
    BottomNavigation
  },
  computed: {
    // miniVariant () {
    //   switch (this.$vuetify.breakpoint.name) {
    //     case 'xs':
    //       return true
    //     case 'sm':
    //       return true
    //     case 'md':
    //       return true
    //     case 'lg':
    //       return false
    //     case 'xl':
    //       return false
    //   }
    // }
    miniVariant () {
      return this.$vuetify.breakpoint.mdAndDown
    },
    showLeftHand () {
      return this.$vuetify.breakpoint.mdAndUp
    },
    showRightHand () {
      return this.$vuetify.breakpoint.smAndDown
    },
    title () {
      if (this.$route.name === 'index') {
        return 'Customer'
      }
      return this.$route.name
    }
  },
  data () {
    return {
      clipped: true,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-home',
          title: 'Home',
          to: '/'
        },
        {
          icon: 'mdi-account-group',
          title: 'Customer',
          to: '/customer'
        },
        {
          icon: 'mdi-chart-histogram',
          title: 'Report',
          to: '/inspire'
        },
        {
          icon: 'mdi-download',
          title: 'Download',
          to: '/inspire'
        },
        {
          icon: 'mdi-dots-horizontal',
          title: 'More',
          to: '/inspire'
        }
      ],
      // miniVariant: false,
      right: true,
      rightDrawer: false,
      // title: 'NT-Application',
      threeLineIcon: false
    }
  },
  methods: {
    onClickRoute (routeTo) {
      // this.$route.query(routeTo)
      this.$router.replace(routeTo)
    }
  }
}
</script>

<!--<style lang="scss">-->
<!--div:active {-->
<!--  icon {-->
<!--   color:red;-->
<!--  }-->
<!--}-->
<!--</style>-->
