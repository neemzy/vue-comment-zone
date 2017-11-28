<template>
  <ul class="CommentList" v-if="comments.length > 0">
    <Comment
      v-for="comment in comments"
      :key="comment.id"
      :author="comment.user"
      :postedAt="comment.created_at"
      :body="comment.content"
    />
  </ul>
  <div class="CommentList CommentList--noComment" v-else>{{ noCommentLabel }}</div>
</template>

<script>
import Comment from "./Comment";

export default {
  props: {
    comments: {
      type: Array,
      default: () => []
    },
    noCommentLabel: {
      type: String,
      default: "No comment yet!"
    }
  },
  components: { Comment }
};
</script>
