<template>
  <section class="CommentZone">
    <h1 class="CommentZone__title">{{ zoneTitle }}</h1>
    <CommentList
      :comments="comments"
      :noCommentLabel="noCommentLabel"
    />
    <CommentForm
      v-if="canPost"
      v-model="input"
      :buttonLabel="formButtonLabel"
      @submit="submit"
    />
  </section>
</template>

<script>
import CommentList from "./CommentList";
import CommentForm from "./CommentForm";

export default {
  props: {
    comments: {
      type: Array,
      default: () => []
    },
    canPost: {
      type: Boolean,
      default: true
    },
    zoneTitle: {
      type: String,
      default: "Comments"
    },
    noCommentLabel: {
      type: String,
      default: "There is nothing here yet."
    },
    formButtonLabel: {
      type: String,
      default: "Submit"
    }
  },
  data() {
    return {
      input: ""
    };
  },
  watch: {
    comments() {
      this.input = ""; // comment was posted successfully, clear form
    }
  },
  methods: {
    submit() {
      this.$emit("submit", this.input);
    }
  },
  components: { CommentList, CommentForm }
};
</script>
