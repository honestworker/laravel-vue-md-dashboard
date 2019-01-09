<template>
  <div class="wrapper">
    <notifications></notifications>

    <side-bar :sidebarLinks="siderbarLinks">
      <mobile-menu slot="content"></mobile-menu>
    </side-bar>

    <div class="main-panel">
      <top-navbar></top-navbar>

      <dashboard-content>

      </dashboard-content>

      <content-footer v-if="!$route.meta.hideFooter"></content-footer>
    </div>
  </div>
</template>
<style lang="scss">

</style>
<script>
import TopNavbar from './TopNavbar.vue'
import ContentFooter from './ContentFooter.vue'
import DashboardContent from './Content.vue'
import MobileMenu from '@/pages/Layout/MobileMenu.vue'

export default {
  components: {
    TopNavbar,
    DashboardContent,
    ContentFooter
  },
  data() {
    return {
      siderbarLinks: [
        {
          'name': 'Dashboard',
          'icon': 'dashboard',
          'path': 'dashboard'
        },
        {
          'name': 'User Profile',
          'icon': 'person',
          'path': 'user'
        },
        {
          'name': 'Table list',
          'icon': 'content_paste',
          'path': 'table'
        },
        {
          'name': 'Typography',
          'icon': 'library_books',
          'path': 'typography'
        },
        {
          'name': 'Icons',
          'icon': 'bubble_chart',
          'path': 'icons'
        },
        {
          'name': 'Maps',
          'icon': 'location_on',
          'path': 'maps'
        },
        {
          'name': 'Notifications',
          'icon': 'notifications',
          'path': 'notifications'
        },
        {
          'name': 'Pages',
          'icon': 'pages',
          'children': [
            {
              'name': 'Login',
              'icon': 'exit_to_app',
              'path': 'login'
            },
            {
              'name': 'Signup',
              'icon': 'person_add',
              'path': 'signup'
            }
          ]
        }
      ]
    }
  },
}
</script>
