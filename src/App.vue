<script setup lang="ts">
import { ref } from 'vue';
import ContentSlide from './components/ContentSlide.vue';
import ContentSlideItem from './components/ContentSlideItem.vue'


const slideIndex = ref(0)


</script>

<template>

  <div>
    <ContentSlide :current-index="slideIndex">
      <ContentSlideItem>
        <p>P1</p>
      </ContentSlideItem>
      <ContentSlideItem>
        <p>P2</p>
      </ContentSlideItem>
    </ContentSlide>

    <div>
      <button @click="() => slideIndex--"> << </button>
      <button @click="() => slideIndex++"> >> </button>
    </div>
  </div>

</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
