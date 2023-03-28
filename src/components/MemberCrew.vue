<template>
    <article class="section crew-member" :class="{'crew-member__active': isActive}">
      <img class="crew-member__image" :src="member.image" :alt="member.name" loading="lazy">
      <div class="container-info">
        <span class="crew-member__name">{{ member.name }}</span>
        <p class="crew-member__position">{{ member.rol }}</p>
      </div>
    </article>
  </template>
  
  <script>
  export default {
    name: "MemberCrew",
    props: {
      member: Object,
      isActive: Boolean
    }
  };
  </script>
  