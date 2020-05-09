<template>
  <b-container class="bv-example-row conts">
    <b-row>
      <b-col md="9">
        <Featured :keyword="keyword" :name="featured.title" :src="featured.url" :paragraph="metadot"/>
        <b-row>
            <b-col md="12">
                <h3 class="subtitle">Gallery of {{keyword}}</h3>
            </b-col>
            <Gallery v-for="gallery in galleries" :title="gallery.title" :url="gallery.url" :alt="gallery.alt" />
        </b-row>
      </b-col>
      <b-col md=3>
        <div class="sidebar">
          <h3>Popular Post</h3>
          <ul>
            <SidebarPopular v-for="sidepop in sidebars" :name="sidepop.keyword" :slug="sidepop.slug" :uuid="sidepop.cat_id" />
          </ul>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import axios from 'axios';
import Featured from '../../../../components/Single/Featured';
import Gallery from '../../../../components/Single/Gallery';
import SidebarPopular from '../../../../components/Single/SidebarPopular';

export default {
    components: {
        Featured,
        Gallery,
        SidebarPopular
    },
    data() {
        return {
            galleries: [],
            featured: [],
            sidebars: [],
            keyword: '',
            metadot: '',
            metacom: ''
        }
    },
    async created(){
        const config = {
            headers: {
                'Accept': 'application/json'
            }
        }
        try {
            const res = await axios.get(`https://power.vpnlabs.xyz/api/v1/wallpaper/get/${this.$route.params.id}/${this.$route.params.slug}`, config);
            if (res.data.status == 404) {
              location.href = '/';
            } else {
              this.keyword = res.data.keyword;
              this.featured = res.data.featured;
              this.galleries = res.data.data;
              this.metadot = res.data.meta.dot;
              this.metacom = res.data.meta.comma;
            }
            
        } catch (error) {
            console.log(error);
        }
        
        try {
            const side = await axios.get(`https://power.vpnlabs.xyz/api/v1/keyword/${this.$route.params.id}/10`, config);
            this.sidebars = side.data.data;
        } catch (sideerror) {
            console.log(sideerror);
        }
    },
    head() {
        return {
            title: this.keyword + ' - ' + this.metadot,
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: this.metadot
                },
                {
                    hid: 'keywords',
                    name: 'keywords',
                    content: this.metacom
                }
            ]
        }
  }
}
</script>
<style>
  .conts{
    margin-top: 80px;
    padding: 20px;
    background: #f8f8f8;
    border-radius: 5px;
  }
  .conts h1 {
    font-size: 1rem;
  }
  .conts h3 {
    font-size: 20px;
    text-align: center;
  }
  .sidebar ul {
    maring: 0;
    padding: 2px;
    list-style: none;
  }
  .sidebar li a {
    width: 100%;
    display: block;
    color: #333;
    text-align: center;
    font-size: 15px;
  }
  .sidebar a:hover {
    text-decoration: none;
  }
</style>