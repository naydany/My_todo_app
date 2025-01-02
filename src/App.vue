<template>
  <v-app>
    <!-- <v-app-bar title="Application bar"></v-app-bar> -->
    <v-toolbar>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>
        <RouterLink to="/">Vuetify</RouterLink>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <!-- <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn> -->
      <v-menu>
        <template v-slot:activator="{ props }">
          <!-- <v-btn color="primary" v-bind="props"> Activator slot </v-btn> -->
          <v-btn icon class="text-none" stacked v-bind="props">
            <v-badge color="red-darken-2" content="6" size="x-small">
              <v-icon icon="mdi-bell" color="blue-darken-4"></v-icon>
            </v-badge>
          </v-btn>
        </template>
        <v-list>
          <v-list-item
            v-for="(item, index) in notifications"
            :key="index"
            :value="index"
          >
            <v-list-item-title>
              <v-icon :color="item.color" :icon="item.icon"></v-icon>
              {{ item.title }}
            </v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>

      <v-btn
        to="/login"
        variant="outlined"
        color="red-darken-4"
        size="default"
        text="login"
      >
        Login
      </v-btn>
    </v-toolbar>
    <v-main>
      <v-slide-x-transition>
        <RouterView />
      </v-slide-x-transition>
    </v-main>
  </v-app>
</template>
<script setup lang="js">
import { RouterView } from "vue-router";

const notifications = [
  { title: "Messages 1", icon: "mdi-message", "color": "blue"},
  { title: "Mesages 2", icon: "mdi-message", "color": "red"},
  { title: "Messages 3", icon: "mdi-message", "color": "pink"},
  { title: "Messages 4", icon: "mdi-message", "color": "yellow"},
  { title: "Messages 5", icon: "mdi-message", "color": "orange"},
  { title: "Messages 6", icon: "mdi-message", "color": "blue"},
];
</script>
