<template>
  <v-app dark app>
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
            <img :src="item.icon" />
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <img :src="titleIcon" class="mx-3" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: true,
      drawer: true,
      fixed: true,
      items: [
        {
          icon: 'https://img.icons8.com/material-outlined/24/000000/home--v2.png',
          title: 'Inicio',
          to: '/',
        },
        {
          icon: 'https://img.icons8.com/carbon-copy/24/000000/morty-smith.png',
          title: 'Personajes',
          to: '/personajes',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      titleIcon: 'https://img.icons8.com/color/48/000000/rick-sanchez.png',
      title: 'Rick and Morty',
    }
  },
}
</script>
