<!-- https://markus.oberlehner.net/blog/multi-export-vue-single-file-components-with-proxy-exports/ -->

<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app>
      <!--  -->
      <v-list-item class="px-2">
        <v-list-item-avatar
          v-if="userAvatarImage === true"
          key="userAvatar-imageTrue"
        >
          <v-img src="https://randomuser.me/api/portraits/men/85.jpg"></v-img>
        </v-list-item-avatar>
        <v-list-item-avatar v-else color="primary" size="35">
          <span class="white--text text">CJ</span>
        </v-list-item-avatar>

        <v-list-item-title>John Leider</v-list-item-title>

        <v-btn icon @click.stop="drawer = !drawer">
          <v-icon>mdi-chevron-left</v-icon>
        </v-btn>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item v-for="item in items" :key="item.title" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Variance Analysis</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <!--  -->
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: true,
    items: [
      { title: "Home", icon: "mdi-view-dashboard" },
      { title: "Upload Files", icon: "mdi-folder-upload-outline" },
      { title: "Variance Analysis", icon: "mdi-chart-gantt" },
      { title: "Users", icon: "mdi-account-group-outline" },
      { title: "My Account", icon: "mdi-account-outline" },
    ],
    mini: true,
  }),
};
</script>
