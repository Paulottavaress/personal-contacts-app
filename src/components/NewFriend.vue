<template>
  <form @submit.prevent="submitData">
    <div>
      <label>Name</label>
      <input type="text" name="name" v-model="name">
    </div>
    <div>
      <label>Phone</label>
      <input type="text" name="phone" v-model="phone">
    </div>
    <div>
      <label>Email</label>
      <input type="email" name="email" v-model="email">
    </div>
    <div>
      <label>Favorito?</label>
      <input type="checkbox" name="isFavorite" v-model="isFavorite">
    </div>
    <button type="submit">Add</button>
  </form>
</template>

<script>
  export default {
    data () {
      return {
        name: '',
        phone: '',
        email: '',
        isFavorite: false
      }
    },
    emits: ['add-contact'],
    methods: {
      submitData () {
        this.$emit('add-contact', {
          name: this.name,
          phone: this.phone,
          email: this.email,
          isFavorite: this.isFavorite
        });
      }
    }
  }
</script>

<style></style>