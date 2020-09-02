<template>
  <div class="home">
    <Header>My Memos</Header>
    <ul v-for="memo in newest" :key="memo.id">
      <li>
        <router-link :to="{name:'Edit',params:{id:memo.id}}">{{memo.body}}</router-link>
        <!-- router/index.jsで指定しているnameのpathを持ってくる。 -->
      </li>
    </ul>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";

export default {
  name: "home",
  components: {
    Header,
  },
  //It's caluculate when it is called.
  computed: {
    newest: function () {
      return this.$store.state.memos.slice().reverse();
    },
  },
};
</script>
