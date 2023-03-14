<template>
  <article class="work">
    <div class="work-info">
      <span class="work-title">{{ title }}</span>
      <p class="work-description">{{ description }}</p>
    </div>
    <div class="work-image__container">
      <img class="work-image" :src="imgUrl" :alt="title">
    </div>
  </article>
</template>

<script>
export default {
  name: "WorkComponent",
  props: {
    title: String,
    imgUrl: String,
    description: String
  },
};
</script>
