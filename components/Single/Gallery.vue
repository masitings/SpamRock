<template>
  <b-col md="3" class="galleryItem">
    <div class="galleryImg">
        <b-img-lazy :src="url" class="imgGall" blank-src="/loader.gif" :alt="alt" :title="title" onerror="this.onerror=null;this.src='/blank.png';" />
        <button :data-src="url" v-scroll-to="'#featuredClass'" class="btn-secondary btn-block" @click="changeFeatured">Preview</button>
    </div>
  </b-col>
</template>

<script>
import $ from 'jquery';

export default {
    name: 'Gallery',
    props: ['title', 'url', 'alt', 'domain', 'source'],
    methods: {
        changeFeatured: function(event)
        {
            var fClasss = $('#featuredClass');
            var imgClass = event.target.getAttribute('data-src');
            $('#featuredClass').attr('src', imgClass);
            window.scrollTo(0,0)
        }
    }
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