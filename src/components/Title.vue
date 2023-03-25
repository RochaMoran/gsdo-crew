<template>
   <h3 class="works-title">
    <span>{{title}}</span>
  </h3>
</template>

<script>

export default {
  name: "TitleComponent",
  props: {
    title: String,
  },
};
</script>
