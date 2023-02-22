<template>
    <li>
      <h2>{{ friend.name }} {{ (friend.isFavorite) ? ('(Favorite)') : '' }}</h2>
      <button @click="toggleDetails">{{ detailsAreVisible ? 'Hide' : 'Show' }} Details</button>
      <button @click="this.$emit('toggle-favorite', friend.id)">Toggle Favorite</button>
      <ul :style="{ display: detailsAreVisible ? 'block' : 'none'}">
        <li><strong>Phone:</strong> {{ friend.phone }}</li>
        <li><strong>Email:</strong> {{ friend.email }}</li>
      </ul>
      <button @click="this.$emit('delete-friend', friend.id)">Delete</button>
    </li>
</template>

<script>
  export default {
    props: {
      friend: {
        type: Object,
        required: true
      }
    },
    emits: [
      'toggle-favorite',
      'delete-friend'
    ],
    data() {
      return {
        detailsAreVisible: false
      };
    },
    methods: {
      toggleDetails() {
        this.detailsAreVisible = !this.detailsAreVisible;
      },
    }
  };
</script>

<style>

</style>