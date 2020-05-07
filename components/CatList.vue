<template>
  <nuxt-link :to="'/single/'+ uuid +'/' + slug">
    <div class="content">
        <p>{{ catlist }}</p>
    </div>
  </nuxt-link>
</template>

<script>
export default {
    name: 'CatList',
    props: ['catlist', 'slug', 'uuid']
}
</script>

<style>
    .content {
        padding: 1rem;
        border: 1px dotted #ccc;
        margin: 1rem 0;
    }
</style>