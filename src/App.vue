<script>
import { marked } from 'marked';
import { debounce } from "lodash-es";
export default {
  data() {
    return {
      input: "# hello"
    }
  },
  computed: {
    output() {
      return marked(this.input)
    }
  },
  methods: {
    update: debounce(function (e) {
      this.input = e.target.value;
    }, 100)
  }
}
</script>

<template>
  <textarea :value="input" @input="update"></textarea>
  <div v-html="output"></div>
</template>

<style>
</style>
