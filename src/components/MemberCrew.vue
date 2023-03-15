<template>
    <article class="section crew-member">
      <div class="container-info">
        <span class="crew-member__name">{{ member.name }}</span>
        <p class="crew-member__position">{{ member.rol }}</p>
      </div>
      <img class="crew-member__image" :src="member.image" :alt="member.name">
    </article>
  </template>
  
  <script>
  export default {
    name: "MemberCrew",
    props: {
      member: Object
    }
  };
  </script>
  