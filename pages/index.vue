<template>
  <section class="section">
    <b-field>
      <b-input placeholder="Search..." expanded></b-input>
      <p class="control">
        <button class="button is-primary">Search</button>
      </p>
    </b-field>
    <div class="columns is-mobile">
      <card title="จำนวนผู้รับบริการ" icon="account-alert">
        <b class="has-text-grey"> จำนวนผู้รับบริการ </b>
      </card>

      <card title="งานทั้งหมด" icon="desktop-classic">
        <b class="has-text-grey"> งานทั้งหมด </b>
      </card>

      <card title="สถานะ" icon="alert-decagram">
        <b class="has-text-grey"> สถานะ </b>
      </card>

      <card title="หน่วยงานที่ใช้บริการสูงสุด" icon="home-map-marker">
        <b class="has-text-grey"> หน่วยงานที่ใช้บริการสูงสุด </b>
      </card>
    </div>
  </section>
</template>

<script>
import Card from '~/components/Card'

export default {
  name: 'HomePage',

  components: {
    Card,
  },
}
</script>
