<template>
  <div id="inputComponent">
    <input
      :placeholder="placeholder"
      v-model="input"
      v-on:keyup.enter="monitorEnterKey"
      class="input is-small"
      type="text"
    >
    <button v-on:click="monitorEnterKey">Add 1</button>
  </div>
</template>

<script>
export default {
  name: "inputComponent",
  props: ["placeholder"],
  data() {
    return {
      input: ""
    };
  },
  methods: {
    monitorEnterKey() {
      this.$emit("add-note", {
        note: this.input,
        timestamp: new Date().toLocaleString()
      });
      //alert("le has dado al enter");
      this.input = "";
    }
  }
};
</script>
