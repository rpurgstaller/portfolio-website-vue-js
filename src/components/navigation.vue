<template>
    <div class="center" id="nav">
      <div >
      </div>
      <div>
        <vs-navbar center-collapsed v-model="active" class="navbar">
          <template #left>
            <a href="/">rp</a>
          </template>
          <template #right>
            <div v-if="!isMobile()">
              <vs-navbar-item
                v-for="(textItem, idx) in textItems"
                :key="'txt' + idx"
                :active="active == textItem.value"
                :to="'/' + textItem.value"
                :id="textItem.value"
                :target="textItem.target"
              >
                {{ textItem.displayName }}
              </vs-navbar-item>
            </div>
            <div v-if="!isMobile()">
              <vs-navbar-item
                v-for="(mediaIcon, idx) in mediaIcons"
                :key="'media' + idx"
                target='_blank'
                :href="mediaIcon.ref"
                :id="mediaIcon.value"
              >
                <v-icon :name="mediaIcon.iconName"/>
              </vs-navbar-item>
            </div>
            <vs-navbar-item
              v-if="isMobile()"
              @click="activeSidebar = !activeSidebar"
            >
              <v-icon name='bars'/>
            </vs-navbar-item>
          </template>
        </vs-navbar>
        <!-- sidebar -->
        <vs-sidebar
          right
          v-model="active"
          :open.sync="activeSidebar"
        >
          <vs-sidebar-item
            v-for="(textItem, idx) in textItems"
            :key="'mTxt' + idx"
            :to="'/' + textItem.value"
            @click.native="activeSidebar = false"
          >
            {{ textItem.displayName }}
          </vs-sidebar-item>
        </vs-sidebar>
      </div>
    </div>
</template>

<script>
export default {
  name: 'Navbar',
  data: () => {
    return {
      active: 'home',
      activeSidebar: false,
      textItems: [
        { value: 'about', displayName: 'about' },
        { value: 'projects', displayName: 'projects' },
        { value: 'contact', displayName: 'contact' }
      ]
    }
  },
  methods: {
    getTextItems: function () {
      if (this.$mq === 'mobile') {
        return []
      }
      return this.textItems
    },
    isMobile: function () {
      return this.$mq === 'mobile'
    }
  }
}
</script>

<style>
  .navbar {
    background: rgba(255, 165, 0, 0.0) !important;
  }

  .vs-navbar__item {
    color: #123456;
  }
</style>
