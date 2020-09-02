<template>
  <div class="editor">
    <Header>Edit Memo</Header>
    <textarea name="memo" v-model="memoBody"></textarea>
    <button @click="save3">Save</button>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";

export default {
  name: "edit",
  components: {
    Header,
  },
  data: function () {
    return {
      memoBody: "",
    };
  },
  //Run below when you visit our site.
  mounted: function () {
    let id = this.$route.params["id"];
    let memo = this.$store.state.memos.find((memo) => memo.id == id);
    this.memoBody = memo.body;
  },
  methods: {
    save3: function () {
      this.$store.commit("update", {
        id: this.$route.params["id"],
        body: this.memoBody,
      });
      this.$router.push("/");
    },
  },
};
</script>
