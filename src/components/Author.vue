<template>
  <div class="author">
    <g-link to="/">
      <g-image
        alt="Author image"
        class="author__image"
        src="../assets/photo-author.jpg"
        width="180"
        height="180"
        blur="5"
      />
    </g-link>

    <h1 v-if="showTitle" class="author__site-title">
      {{
      $static.metadata.siteName
      }}
    </h1>

    <!-- <p class="author__links">
      <a href="//gryaznoff.com" target="_blank" rel="noreferrer">Webpage</a>
      <a href="//facebook.com/vyacheslav.gryaznov" target="_blank" rel="noreferrer">Facebook</a>
      <a href="//youtube.com/VyacheslavGryaznovPiano" target="_blank" rel="noreferrer">YouTube</a>
      <a href="//mailto:gryaznov.studio@gmail.com" target="_blank" rel="noreferrer">@email</a>
    </p>-->
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
export default {
  props: ["showTitle"]
};
</script>

<style lang="scss">
.author {
  margin: 0 auto;
  margin-top: -2rem;
  max-width: 100%;
  text-align: center;
  padding: calc(var(--space) / 2) 0;
  margin-bottom: 1rem;

  a:hover,
  a:focus {
    border-bottom: none;
  }

  &__image {
    border-radius: 100%;
    width: 180px;
    height: 180px;
    margin-bottom: 1em;
    &:hover {
      transition: scale(1.1);
    }
  }

  &__intro {
    opacity: 0.8;
  }

  &__site-title {
    font-size: 2rem;
  }

  &__links {
    margin-top: -0.5em;
    a {
      margin: 0 0.3em;
      &:hover,
      &:focus {
        border-bottom: 1px solid var(--link-color-p);
      }
    }
  }
}
</style>
