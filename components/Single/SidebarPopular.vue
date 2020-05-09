<template>
    <li>
        <nuxt-link :to="'/single/'+ uuid +'/'+slug">
            {{name}}
        </nuxt-link>
    </li>
</template>

<script>
export default {
    name: 'SidebarPopular',
    props: ['name', 'slug', 'uuid']
}
</script>

<style>
    .sidebar {
        width: 100%;
        border: 1px solid #c6c6c6;
        border-radius: 5px;
    }
    .sidebar h3 {
        font-size: 20px;
        text-align: center;
        background:#6c757d;
        color: white;
        padding: 5px;
    }

</style>