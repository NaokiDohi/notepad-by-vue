<template>
  <div class="editor">
    <h1>Edit Memo</h1>
    <textarea name="memo" v-model="memoBody"></textarea>
    <button @click="save3">Save</button>
  </div>
</template>

<script>
export default {
  name: "edit",
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
