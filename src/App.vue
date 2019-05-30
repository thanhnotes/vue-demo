<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span class='amber--text'>Todo</span>
        <span class="font-weight-light">-List</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        flat
        href="https://google.com"
        target="_blank"
      >
        <span class="mr-2">Google Phát!</span>
      </v-btn>
    </v-toolbar>

    <v-content>
      <router-view></router-view>
    </v-content>

  </v-app>
</template>

<script>

export default {
  name: 'App',

  data () {
    return {
      //
    }
  }
}
</script>
