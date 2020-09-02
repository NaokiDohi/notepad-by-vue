<template>
  <div class="editor">
    <h1>New Memo</h1>
    <textarea name="memo" v-model="memoBody"></textarea>
    <button @click="save">Save</button>
  </div>
</template>

<script>
export default {
  name: "new",
  data: function () {
    return {
      memoBody: "",
    };
  },
  methods: {
    save: function () {
      this.$store.commit("save2", {
        body: this.memoBody,
      });
      this.$router.push("/");
    },
  },
};
</script>


