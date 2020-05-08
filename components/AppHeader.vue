<template>
    <b-navbar toggleable="lg" fixed="top" type="dark" variant="secondary">
        <b-container>
            <b-navbar-brand href="/">Home Design Platform</b-navbar-brand>
            <b-navbar-toggle target="nav_collapse" />
            <b-collapse is-nav id="nav_collapse">
                <b-navbar-nav>
                    <li class="navbar-nav">
                        <nuxt-link class="nav-link" :to="'/'">Home</nuxt-link>
                    </li>
                    <li class="navbar-nav">
                        <nuxt-link class="nav-link" :to="'/category'">Category</nuxt-link>
                    </li>
                </b-navbar-nav>
            </b-collapse>
        </b-container>
    </b-navbar>
</template>

<script>
export default {
    name: 'AppHeader'
}
</script>

<style>

</style>