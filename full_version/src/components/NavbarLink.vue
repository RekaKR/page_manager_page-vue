<template>
  <a class="nav-link" :class="activeClasses" :href="page.link.url" :title="`This Link goes to the ${page.link.text} page`"
    aria-current="page">{{
      page.link.text }}
  </a>
</template>

<script>
export default {
  props: ['page', 'isActive'],
  computed: {
    activeClasses() {
      return {
        active: this.isActive,
        emphasize: this.Active
      }
    }
  }

}
</script>
