<template>
  <nav :class="[`navbar-${theme}`, `bg-${theme}`, 'navbar', 'navbar-expand-lg']">
    <div class="container-fluid">
      <a href="#" class="navbar-brand">My Vue</a>

      <ul class="navbar-nav me-auto mb-2 mb-lg-8">
        <li class="nav-item" v-for='(page, index) in pages' :key="index">
          <navbar-linik :page="page" :isActive="activePage === index" @click.prevent="navLinkClick(index)"></navbar-linik>
        </li>
      </ul>

      <form class="d-flex">
        <button class="btn btn-primary" @click.prevent="changeTheme()">Toggle</button>
      </form>
    </div>
  </nav>
</template>

<script>
import NavbarLink from './NavbarLink.vue';

export default {
  components: {
    NavbarLink
  },
  props: ['pages', 'activePage', 'navLinkClick'],
  data() {
    return {
      theme: 'light',
    }
  },
  methods: {
    changeTheme() {
      /*let bla = 'light'
      
      if (this.theme === 'light') {
        bla = 'dark'
      }
      
      this.theme = bla*/
      this.theme = this.theme === 'light' ? 'dark' : 'light'
    }
  }
}
</script>
