<template>
  <button
    role="button"
    aria-label="Toggle dark/light"
    @click.prevent="toggleTheme"
    class="toggle-theme"
  >
    <img
      v-if="darkTheme"
      src="../assets/images/milk.svg"
      width="30"
      height="30"
      alt="light theme icon"
    />
    <img v-else src="../assets/images/coffee.svg" width="30" height="30" alt="dark theme icon" />
  </button>
</template>

<script>
export default {
  data() {
    return {
      darkTheme: false
    };
  },
  methods: {
    toggleTheme() {
      this.darkTheme = !this.darkTheme;

      // This is using a script that is added in index.html
      window.__setPreferredTheme(this.darkTheme ? "dark" : "light");
    }
  },
  mounted() {
    if (window.__theme == "dark") this.darkTheme = true;
  }
};
</script>

<style lang="scss">
.toggle-theme {
  margin: 1rem;
  padding: 0;
  background-color: transparent;
  border: 0;
  color: var(--body-color);
  cursor: pointer;

  &:hover {
    opacity: 0.8;
    border: 0;
  }
  &:focus {
    outline: none;
    border: 0;
  }
  img {
    margin-bottom: 0;
    transition: opacity 1s;
    &:focus,
    &:active {
      outline: none;
    }
  }
}
</style>