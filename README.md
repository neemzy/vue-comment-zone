# vue-comment-zone

Simple comment system Vue.js components

## Usage

```html
<template>
  <CommentZone
    :comments="comments"
    :canPost="canPost"
    :zoneTitle="zoneTitle"
    :noCommentLabel="noCommentLabel"
    :buttonFormLabel="buttonFormLabel"
    @submit="submitComment"
  />
</template>

<script>
import CommentZone from "vue-comment-zone";

export default {
  data() {
    comments: [], // cf. infra
    canPost: true // whether to display the form
    zoneTitle: "Comments",
    noCommentLabel: "There is nothing here yet.",
    buttonFormLabel: "Submit"
  },
  methods: {
    /**
     * @param {String} comment
     */
    submitComment(comment) {}
  },
  components: { CommentZone }
};
</script>

<style scoped>
.CommentZone {}
.CommentZone__title {}

.CommentList {}
.CommentList--noComment {}

.Comment {}
.Comment__author {}
.Comment__authorName {}
.Comment__authorAvatar {}
.Comment__postedAt {}
.Comment__body {}

.CommentForm {}
.CommentForm__input {}
.CommentForm__button {}
</style>
```

## Comment object format

```js
{
  author: {
    name: String,
    avatar: String,
  },
  postedAt: String,
  body: String
}
```
