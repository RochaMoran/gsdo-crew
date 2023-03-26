<template>
  <div class="work">
    <div class="work-image__container">
      <img class="work-image" :src="img" :alt="title">
      <span class="work-title">{{ title }}</span>
    </div>
  </div>
</template>

<script>

export default {
  name: "WorkComponent",
  props: {
    title: String,
    img: String,
  },
  mounted() {
    const options = {
      rootMargin: '0px',
      threshold: 1.0
    };
    
    const observer = new IntersectionObserver((entries, observer) => {
      entries.forEach(entry => {
        if (entry.intersectionRatio === 1) {
          entry.target.classList.add('show-item');
          observer.unobserve(entry.target);
        }
      });
    }, options);

    observer.observe(this.$el);
  },
};
</script>
