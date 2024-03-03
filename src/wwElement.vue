<template>
  <div>
    Drag me to the Novel Editor
    <Editor class="editor"  v-on:update="onUpdate()"
      v-on:debouncedUpdate="debouncedUpdate()" />
  </div>
</template>

<script>
import { Editor } from "novel-vue";
import "novel-vue/dist/style.css";
export default {
  components: {
    Editor
  },
  props: {
    defaultValue: Object
  },
  methods: {
    onUpdate() {
      console.log("On update Triggered")
    },
    debouncedUpdate() {
      console.log("On Debounced Update")
    },
  },
  computed: {
    textStyle() {
      return {
        color: this.content.textColor,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
p {
  color: green
}

.editor {
  border: 1px solid grey;
}</style>
