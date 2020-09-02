<template>
  <div class="editor">
    <h1>Edit Memo</h1>
    <textarea name="memo" v-model="memo.body"></textarea>
    <button @click="save3">Save</button>
  </div>
</template>

<script>
export default {
  name: "edit",
  computed: {
    memo: function () {
      let id = this.$route.params["id"];
      return this.$store.state.memos.find((memo) => memo.id == id);
    },
  },
  methods: {
    save3: function () {
      this.$store.commit("update", {
        id: this.memo.id,
        body: this.memo.body,
      });
      this.$router.push("/");
    },
  },
};
</script>
