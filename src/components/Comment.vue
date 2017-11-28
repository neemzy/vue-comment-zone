<template>
  <li class="Comment">
    <div class="Comment__author">
      <img :src="author.avatar" class="Comment__authorAvatar" />
      <span class="Comment__authorName">{{ author.name }}</span>
    </div>
    <div class="Comment__postedAt">{{ postedAt }}</div>
    <div class="Comment__body">{{ body }}</div>
  </li>
</template>

<script>
export default {
  props: {
    author: {
      type: Object,
      default: () => {}
    },
    postedAt: {
      type: String,
      default: ""
    },
    body: {
      type: String,
      default: ""
    }
  }
};
</script>
