<template>
  <nav class="navbar">
    <ul class="navbar-list">
      <li v-for="item in sections" :key="item.id">
        <a :href="item.link">{{ item.title }}</a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
  data () {
    return {
      sections: [
        { id: 1, title: 'Crew', link: "#crew" },
        { id: 2, title: 'Works', link: "#works" },
        { id: 3, title: 'Contact', link: "#contact" },
        { id: 4, title: 'Clients', link: "#clients" }
      ],
    }
  },
};
</script>
