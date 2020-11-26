<template>
  <aside class="column is-2 section">
    <p class="menu-label is-hidden-touch">เมนู</p>
    <ul class="menu-list">
      <li v-for="(item, key) of items" :key="key">
        <nuxt-link :to="item.to" exact-active-class="is-active">
          <b-icon :icon="item.icon" /> {{ item.title }}
        </nuxt-link>
      </li>
    </ul>
  </aside>
</template>
<script>
export default {
  data() {
    return {
      items: [
        {
          title: 'Home',
          icon: 'home',
          to: { name: 'index' },
        },
        {
          title: 'บันทึกงาน',
          icon: 'account-box-multiple',
          to: { name: 'jobs' },
        },
        {
          title: 'Inspire',
          icon: 'lightbulb',
          to: { name: 'inspire' },
        },
      ],
    }
  },
}
</script>
