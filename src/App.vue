<template>
  <div id="app">
    <div class="notes-section">
      <div class="columns">
        <div class="column has-text-centered">
          <strong>Notes</strong>
          <div v-for="note in notes" v-bind:key="note.id" class="notes">{{note}}</div>
        </div>
        <div class="column has-text-centered">
          <strong>Timestamp</strong>
          <div
            v-for="timestamp in timestamps"
            v-bind:key="timestamp.id"
            class="timestamps"
          >{{ timestamp }}</div>
        </div>
      </div>
      <input-component @add-note="addNote" :placeholder="placeholder"></input-component>
    </div>
  </div>
</template>

<script>
import inputComponent from "@/components/inputComponent";
import "bulma/css/bulma.css";
export default {
  name: "HelloWorld",
  components: {
    inputComponent
  },
  data() {
    return {
      notes: [],
      timestamps: [],
      placeholder: "Enter a note"
    };
  },
  methods: {
    addNote(event) {
      this.notes.push(event.note);
      this.timestamps.push(event.timestamp);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
