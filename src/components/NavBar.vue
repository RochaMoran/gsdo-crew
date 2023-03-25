<template>
  <nav class="navbar" :class="{'navbar-active': currentSection !== '#header' && currentSection !== null}">
    <ul class="navbar-list">
      <li v-for="item in sections" :key="item.id" :class="{'nav-item__active': currentSection === item.link}">
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
        { id: 1, title: 'Work', link: "#works" },
        { id: 2, title: 'Crew', link: "#crew" },
        { id: 3, title: 'Clients', link: "#clients" },
        { id: 4, title: 'Contacts', link: "#contact" },
      ],
      currentSection: "#works"
    }
  },
  mounted() {
    window.addEventListener('scroll', () => {
      this.currentSection = this.getCurrentSection();
    });
  },
  methods: {
    getCurrentSection() {
      const sections = document.querySelectorAll('section');
      for (let i = 0; i < sections.length; i++) {
        const section = sections[i];
        if (section.offsetTop <= window.scrollY + 50 && section.offsetTop + section.offsetHeight > window.scrollY + 50) {
          return "#" + section.id;
        }
      }
      return null;
    }
  }
};
</script>
