<template>
    <div class="featured">
        <h1>{{keyword}}</h1>
              <b-img-lazy :src="src" fluid :alt="name" :title="keyword" />
        <h2>{{name}}</h2>
        <p>{{paragraph}}</p>
    </div>
</template>

<script>
export default {
    name: 'Featured',
    props: ['keyword', 'name', 'src', 'paragraph']
}
</script>

<style>
    .featured h1 {
        font-size: 1.3rem;
        line-height: 1.2;
    }
    .featured h2 {
        margin-top: 10px;
        font-size: 1rem;
        line-height: 1.2;
        text-align: center;
        font-weight: lighter;
    }
    .featured img {
        width: 100%;
        border-radius: 5px;
    }
    .featured p {
        margin-top: 10px;
        font-size: 12px;
        text-align: justify;
    }
</style>