<template>
  <b-container class="bv-example-row conts">
    <b-row>
      <b-col md="9">
        <Featured :keyword="keyword" :name="featured.title" :src="featured.url" :paragraph="metadot"/>
      </b-col>
      <b-col md=3>
        
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import axios from 'axios';
import Featured from '../../../../components/Single/Featured';

export default {
    components: {
        Featured
    },
    data() {
        return {
            gallery: [],
            featured: [],
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
            this.keyword = res.data.keyword;
            this.featured = res.data.featured;
            this.gallery = res.data.data;
            this.metadot = res.data.meta.dot;
            this.metacom = res.data.meta.comma;
            console.log(res.data);
        } catch (error) {
            console.log(error);
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
</style>