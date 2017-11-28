<template>
  <form class="CommentForm" @submit.prevent="submit">
    <textarea
      name="comment"
      class="CommentForm__input"
      :value="value"
      @input="input"
    ></textarea>
    <button type="submit" class="CommentForm__button">{{ buttonLabel }}</button>
  </form>
</template>

<script>
export default {
  props: {
    value: {
      type: String,
      default: ""
    },
    buttonLabel: {
      type: String,
      default: ""
    }
  },
  methods: {
    input(event) {
      this.$emit("input", event.target.value);
    },
    submit() {
      this.$emit("submit");
    }
  }
};
</script>
