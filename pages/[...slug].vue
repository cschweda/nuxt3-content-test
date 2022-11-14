akh
<template>
  <main>
    <ContentRenderer :value="page" />
  </main>
</template>

<script setup>
const route = useRoute();
const { data: page } = await useAsyncData(
  'page-data-' + route.params.slug,
  () => queryContent('/', ...route.params.slug).findOne()
);
</script>
