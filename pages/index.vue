<template>
  <b-container class="bv-example-row conts">
    <b-row>
      <b-col class="mb-4" md="12">
        <h3>Welcome to {{sitename}}</h3>
      </b-col>
      <ContentIndex v-for="content in contents" :key="content.slug" :slug="content.slug" :uuid="content.cat_id" :content="content.keyword" />
    </b-row>
  </b-container>
</template>

<script>
import axios from 'axios';
import ContentIndex from '../components/ContentIndex';

export default {
  components: {
    ContentIndex
  },
  data() {
    return {
      contents: [],
      title: '',
      keyword: '',
      sitename: ''
    }
  },
  async created() {
      const config = {
          headers: {
              'Accept': 'application/json'
          }
      }
      try {
          const res = await axios.get('http://power.vpnlabs.xyz/api/v1/campaign/d4f2f638-5581-423a-8888-433617fbc155/wallpaper/keyword/100/done', config);
          this.contents = res.data.keyword;
          this.title = res.data.meta.dot;
          this.keyword = res.data.meta.comma;
          this.sitename = location.hostname;
      } catch (error) {
          console.log(error);
      }
  },
  head() {
        return {
            title: this.title,
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: this.title
                },
                {
                    hid: 'keywords',
                    name: 'keywords',
                    content: this.keyword
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
  .conts h3 {
    font-size: 20px;
    text-align: center;
  }
</style>