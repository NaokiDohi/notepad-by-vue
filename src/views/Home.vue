<template>
  <div class="home">
    <ul v-for="memo in newest" :key="memo.id">
      <li>{{memo.body}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "home",
  //It's caluculate when it is called.
  computed: {
    newest: function () {
      return this.$store.state.memos.slice().reverse();
    },
  },
};
</script>
