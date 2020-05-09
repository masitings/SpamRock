<template>
  <b-col md="3" class="galleryItem">
    <div class="galleryImg">
        <b-img-lazy :src="url" blank-src="/loader.gif" :alt="alt" :title="title" onerror="this.onerror=null;this.src='/blank.png';" />
    </div>
  </b-col>
</template>

<script>
export default {
    name: 'Gallery',
    props: ['title', 'url', 'alt', 'domain', 'source'],
}
</script>

<style>
    .galleryItem {
        padding: 0 !important;
    }
    .gallery {
        margin: 0;
    }
    .galleryImg{
        padding: 5px;
    }
    .galleryImg img {
        width: 100%;
        height: 100px;
        box-shadow: 0 1px 2px #888888;
    }
</style>