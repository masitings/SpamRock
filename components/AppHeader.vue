<template>
  <header class="header">
    <h1>Home Design</h1>
    <ul>
        <li><nuxt-link to="/">Home</nuxt-link></li>
        <li><nuxt-link to="/category">Category</nuxt-link></li>
        <li><nuxt-link to="/about">About</nuxt-link></li>
    </ul>
  </header>
</template>

<script>
export default {
    name: 'AppHeader'
}
</script>
<style>
    .header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 1rem;
        padding-bottom: 1rem;
        border-bottom: 1px solid #ccc;
    }
    .header .title {
        font-size: 3rem;
        color: #526488;
    }
    .header ul {
        display: flex;
    }
    .header a {
        display: inline-block;
        background: #333;
        color: #fff;
        padding: 0.3rem 1rem;
        margin-right: 0.5rem;
    }
</style>