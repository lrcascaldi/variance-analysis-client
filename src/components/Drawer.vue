<template>
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

      <v-list-item-title>userName</v-list-item-title>

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
</template>

<script>
export default {
    name: "NavigationDrawer"
  data: () => ({
    userAvatarImage: false,
    userName: "Luiz Cascaldi",
    drawer: true,
    items: [
      { title: "Home", icon: "mdi-view-dashboard" },
      { title: "Upload Files", icon: "mdi-folder-upload-outline" },
      { title: "Variance Analysis", icon: "mdi-chart-gantt" },
      { title: "Users", icon: "mdi-account-group-outline" },
      { title: "My Account", icon: "mdi-account-outline" },
    ],
  }),
};
</script>
