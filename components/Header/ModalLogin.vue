<template>
  <div class="buttons">
    <button class="button is-primary is-medium" @click="cardModal()">
      Launch card modal (Component)
    </button>
  </div>
</template>

<script>
import AddForm from '~/components/ModalForm/AddLog'

export default {
  methods: {
    cardModal() {
      this.$buefy.modal.open({
        parent: this,
        component: AddForm,
        hasModalCard: true,
        customClass: 'custom-class custom-class-2',
        trapFocus: true,
      })
    },
  },
}
</script>
