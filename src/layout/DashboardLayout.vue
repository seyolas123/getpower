<template>
  <div class="wrapper" :class="{ 'nav-open': $sidebar.showSidebar }">
    <side-bar
      :background-color="sidebarBackground"
      short-title="Argon"
      title="Argon"
    >
      <template v-slot:links>
        <sidebar-item
          :link="{
            name: 'Dashboard',
            icon: 'ni ni-tv-2 text-primary',
            path: '/dashboard',
          }"
        />

        <sidebar-item
          :link="{
            name: 'Quick Purchase',
            icon: 'ni ni-planet text-blue',
            path: '/icons',
          }"
        />
        <sidebar-item
          :link="{
            name: 'Maps',
            icon: 'ni ni-pin-3 text-orange',
            path: '/maps',
          }"
        />
        <sidebar-item
          :link="{
            name: 'Transactions',
            icon: 'ni ni-single-02 text-yellow',
            path: '/profile',
          }"
        />
        <sidebar-item
          :link="{
            name: 'Contact Us',
            icon: 'ni ni-bullet-list-67 text-red',
            path: '/tables',
          }"
        />
        <sidebar-item
          :link="{
            name: 'My Meters',
            icon: 'ni ni-key-25 text-info',
            path: '/login',
          }"
        />
        <sidebar-item
          :link="{
            name: 'Virtual Accounts',
            icon: 'ni ni-circle-08 text-pink',
            path: '/register',
          }"
        />
        <sidebar-item
          :link="{
            name: 'My Cards',
            icon: 'ni ni-circle-08 text-pink',
            path: '/register',
          }"
        />
        <sidebar-item
          :link="{
            name: 'Request Utility Bill',
            icon: 'ni ni-circle-08 text-pink',
            path: '/register',
          }"
        />
        <sidebar-item
          :link="{
            name: 'View Profile',
            icon: 'ni ni-circle-08 text-pink',
            path: '/register',
          }"
        />
        <sidebar-item
          :link="{
            name: 'Change Password',
            icon: 'ni ni-circle-08 text-pink',
            path: '/register',
          }"
        />
        <sidebar-item
          :link="{
            name: 'Referrals',
            icon: 'ni ni-circle-08 text-pink',
            path: '/register',
          }"
        />
        <sidebar-item
          :link="{
            name: 'Share',
            icon: 'ni ni-circle-08 text-pink',
            path: '/register',
          }"
        />
      </template>
    </side-bar>
    <div class="main-content" :data="sidebarBackground">
      <dashboard-navbar></dashboard-navbar>

      <div @click="toggleSidebar">
        <!-- your content here -->
        <router-view></router-view>
        <content-footer v-if="!$route.meta.hideFooter"></content-footer>
      </div>
    </div>
  </div>
</template>
<script>
import DashboardNavbar from "./DashboardNavbar.vue";
import ContentFooter from "./ContentFooter.vue";

export default {
  components: {
    DashboardNavbar,
    ContentFooter,
  },
  data() {
    return {
      sidebarBackground: "orange", //vue|blue|orange|green|red|primary
    };
  },
  methods: {
    toggleSidebar() {
      if (this.$sidebar.showSidebar) {
        this.$sidebar.displaySidebar(false);
      }
    },
  },
};
</script>
<style lang="scss"></style>
