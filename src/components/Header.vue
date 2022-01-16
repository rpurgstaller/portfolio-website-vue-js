<template>
  <div class="header-container">
    <header class="header">
      <button v-if="viewport.is768" title="Open menu" type="button" class="header-nav-button" @click="openMenu">
          <v-icon name='bars'/>
      </button>
      <nav class="header-nav">
        <button v-if="viewport.is768" title="Close menu" type="button" class="header-nav-close-button" @click="closeMenu">
          <span class="label">x</span>
        </button>
        <ul>
          <li
            v-for='navItem in navItems'
            :key="navItem.id"
          >
            <router-link :to="'/' + navItem.to">{{ navItem.text }}</router-link>
          </li>
          <li><a href="mailto:roman.purgstaller@protonmail.com">contact</a></li>
          <li><a href="./roman-purgstaller-resume.pdf" target="_blank">cv</a></li>
        </ul>
      </nav>
    </header>
  </div>
</template>

<script>
import '@/styles/header.scss'

export default {
  name: 'Header',
  props: {
    viewport: Object
  },
  data: () => {
    return {
      navItems: [
        { id: 1, to: '', text: 'is' },
        { id: 2, to: 'about', text: 'about' },
        { id: 3, to: 'projects', text: 'projects' }
      ]
    }
  },
  methods: {
    openMenu () {
      document.body.classList.add('-open-nav')
    },
    closeMenu () {
      document.body.classList.remove('-open-nav')
    }
  }
}
</script>
