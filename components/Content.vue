<template>
<nuxt-link :to="'category/' + id">
    <div class="content">
        <p>{{ content }}</p>
    </div>
</nuxt-link>
  
</template>

<script>
export default {
    name: 'Content',
    props: ['content', 'id']
}
</script>

<style>
    .content {
        padding: 1rem;
        border: 1px dotted #ccc;
        margin: 1rem 0;
    }
</style>