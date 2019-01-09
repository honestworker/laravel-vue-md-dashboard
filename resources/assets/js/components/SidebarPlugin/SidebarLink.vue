<template>
  <md-list-item v-bind="$attrs" v-if="link.children" md-expand>
    <slot>
      <md-icon>{{link.icon}}</md-icon>
      <p class="md-list-item-text">{{link.name}}</p>
      <md-list slot="md-expand">
        <md-list-item @click="hideSidebar" v-bind="$attrs" v-for="(subLink, index) in link.children" :key="subLink.name + index"
                        :to="subLink.path"
                        :link="subLink">
        <slot>
          <md-icon>{{subLink.icon}}</md-icon>
          <p class="md-item-text">{{subLink.name}}</p>
        </slot>
        </md-list-item>
      </md-list>
    </slot>
  </md-list-item>
  <md-list-item @click="hideSidebar"
                v-bind="$attrs" v-else>
    <slot>
      <md-icon>{{link.icon}}</md-icon>
      <p class="md-item-text">{{link.name}}</p>
    </slot>
  </md-list-item>
</template>
<script>
export default{
  inject: {
    autoClose: {
      default: true
    }
  },
  props: {
    link: {
      type: [String, Object],
      default: () => {
        return {
          name: '',
          path: '',
          icon: '',
          children: []
        }
      }
    },
    tag: {
      type: String,
      default: 'router-link'
    }
  },
  methods: {
    hideSidebar () {
      if (this.autoClose && this.$sidebar && this.$sidebar.showSidebar === true) {
        this.$sidebar.displaySidebar(false)
      }
    }
  }
}
</script>

<style lang="scss">
</style>
