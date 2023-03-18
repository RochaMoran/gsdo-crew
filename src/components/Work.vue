<template>
  <article class="work">
    <div class="work-info">
      <span class="work-title">{{ title }}</span>
      <p class="work-description">{{ description }}</p>
      <a :href="url" class="work-button" target="_blank">View Project</a>
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
    description: String,
    url: String,
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
