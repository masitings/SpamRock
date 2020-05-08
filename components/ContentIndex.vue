<template>
    <b-col class="columnIndex mb-1" md="6">
        <div class="columnItem">
            <nuxt-link :to="'/single/' + uuid + '/' + slug" :title="content">
                <h2>{{ content }}</h2>
            </nuxt-link>
        </div>
    </b-col>
</template>

<script>
export default {
    name: 'ContentIndex',
    props: ['content', 'uuid', 'name', 'slug']
}
</script>

<style>
    .columnIndex {
        width:100%;
    }
    .columnItem {
        background: #eaeaea;
        padding: 6px;
        width: 100%;
        display: block;
        margin: 4px;
    }
    .columnIndex h2 {
        font-size: 1rem;
        margin: 0;
    }
    .columnIndex a {
        text-decoration: none;
        color: black;
    }
</style>