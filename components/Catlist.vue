<template>
    <b-col md="6" class="mb-4">
        <nuxt-link :to="'/category/' + uuid" :title="catlist" class="catItem">
            <b-card border-variant="secondary" header="" header-bg-variant="dark"  header-text-variant="white" class="text-center">
                <h2>{{catlist}}</h2>
            </b-card>
        </nuxt-link>
    </b-col>
</template>

<script>
export default {
    name: 'Catlist',
    props: ['catlist', 'uuid']
}
</script>

<style>
    .catItem h2 {
        font-size: 1rem;
    }
    .catItem {
        color: black;
        text-decoration: none;
    }
    .catItem:hover {
        text-decoration: none;
        color: black;
        font-weight: 700;
    }
</style>