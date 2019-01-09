<template>
  <div class="sidebar" :data-color="activeColor" :data-image="backgroundImage" :style="sidebarStyle">
    <div class="logo">
      <a href="#" class="simple-text logo-mini">
        <div class="logo-img">
            <img :src="imgLogo" alt="">
        </div>
      </a>

      <a href="https://www.creative-tim.com/product/vue-material-dashboard" target="_blank" class="simple-text logo-normal">
        {{title}}
      </a>
    </div>
    <div class="sidebar-wrapper">
      <slot name="content"></slot>
      <md-list class="nav">
        <!--By default vue-router adds an active class to each route link. This way the links are colored when clicked-->
        <slot>
          <sidebar-link v-for="(link, index) in sidebarLinks"
                        :key="link.name + index"
                        :to="link.path"
                        :link="link">
          </sidebar-link>
        </slot>
      </md-list>
    </div>
  </div>
</template>
<script>
import SidebarLink from './SidebarLink.vue'
import MobileMenu from '@/pages/Layout/MobileMenu.vue'

export default{
  components: {
    SidebarLink,
    MobileMenu
  },
  props: {
    title: {
      type: String,
      default: 'Vue MD'
    },
    backgroundImage: {
      type: String,
      default: require('@/assets/img/sidebar-2.jpg')
    },
    imgLogo: {
      type: String,
      default: require('@/assets/img/vue-logo.png')
    },
    activeColor: {
      type: String,
      default: 'green',
      validator: (value) => {
        let acceptedValues = ['', 'purple', 'blue', 'green', 'orange', 'red']
        return acceptedValues.indexOf(value) !== -1
      }
    },
    sidebarLinks: {
      type: Array,
      default: () => []
    },
    autoClose: {
      type: Boolean,
      default: true
    }
  },
  provide () {
    return {
      autoClose: this.autoClose
    }
  },
  computed: {
    sidebarStyle () {
      return {
        backgroundImage: `url(${this.backgroundImage})`
      }
    }
  }
}
</script>

<style lang="scss">
  @media screen and (min-width: 991px) {
    .nav-mobile-menu{
      display: none;
    }
  }
  .sidebar,
  .off-canvas-sidebar{
    .md-list-item .md-list-item-expand{
      padding: 5px 10px 10px 15px;
    }
    .md-list .md-list-item-expand.md-list-item-container {
      color: var(--md-theme-default-text-primary-on-background, rgb(255, 255, 255));
    }
    .md-list-item-expand{
      &:hover{
        color: #FFFFFF !important;
      }
    }
  }
</style>
