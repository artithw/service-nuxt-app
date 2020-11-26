<template>
  <div>
    <Header />
    <section class="main-content columns">
      <MenuList />

      <div class="container column is-10" style="margin-left: 0px">
        <nuxt />
      </div>
    </section>
  </div>
</template>

<script>
import Header from '@/components/Header/Navbar'
import MenuList from '@/components/Sidebar/MenuList'

export default {
  components: { Header, MenuList },
}
</script>
