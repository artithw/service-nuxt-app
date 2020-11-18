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
  async asyncData({ $axios }) {
    const jobs = await $axios.$get('http://localhost:3030/api/fixlog')
    // eslint-disable-next-line
    console.log(jobs.data)
    return { jobs }
  },
  data() {
    const data = [
      {
        id: 1,
        first_name: 'Jesse',
        last_name: 'Simmons',
        date: '2016-10-15 13:43:27',
        gender: 'Male',
      },
      {
        id: 2,
        first_name: 'John',
        last_name: 'Jacobs',
        date: '2016-12-15 06:00:53',
        gender: 'Male',
      },
      {
        id: 3,
        first_name: 'Tina',
        last_name: 'Gilbert',
        date: '2016-04-26 06:26:28',
        gender: 'Female',
      },
      {
        id: 4,
        first_name: 'Clarence',
        last_name: 'Flores',
        date: '2016-04-10 10:28:46',
        gender: 'Male',
      },
      {
        id: 5,
        first_name: 'Anne',
        last_name: 'Lee',
        date: '2016-12-06 14:38:38',
        gender: 'Female',
      },
    ]

    return {
      jobs: {},
      data,
      selected: data[1],
      columns: [
        {
          field: 'ID',
          label: 'ID',
          width: '40',
          numeric: true,
        },
        {
          field: 'names',
          label: 'First Name',
        },
        {
          field: 'title',
          label: 'title Name',
        },
        {
          field: 'CreatedAt',
          label: 'Date',
          centered: true,
        },
        {
          field: 'agent',
          label: 'Gender',
        },
      ],
    }
  },
}
</script>
