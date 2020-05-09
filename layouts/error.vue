<template>
  <div class="errorpage">
    <div class="content">
        <h1>{{error.statusCode}} Not Found!</h1>
        <p>The page or content are you looking is not found in this website.</p>
        <nuxt-link :to="'/'">Back to Home Page</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
    layout: 'error-layout',
    props: {
        error: {
            type: Object,
            default: null
        }
    },
    head() {
        return {
            title: '404 Not Found!'
        }
    }
}
</script>

<style>
    .errorpage {
        width: 100%;
        text-align: center;
    }
    .content {
        width: 100%;
        margin-top: 100px;
    }
    .content h1 {

    }
</style>