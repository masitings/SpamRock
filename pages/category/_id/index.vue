<template>
  <b-container class="bv-example-row conts">
    <b-row>
      <b-col class="mb-4" md="12">
        <h3>{{this.title}} Category</h3>
      </b-col>
      <ContentIndex v-for="content in contents" :key="content.slug" :slug="content.slug" :uuid="content.cat_id" :content="content.keyword" />
    </b-row>
  </b-container>
</template>

<script>
import axios from 'axios';
import ContentIndex from '../../../components/ContentIndex';

export default {
    components: {
        ContentIndex
    },
    data() {
        return {
            contents: [],
            title: '',
            metacom: '',
            metadot: ''
        }
    },
    async created() {
        const config = {
            headers: {
                'Accept': 'application/json'
            }
        }

        try {
            const res = await axios.get(`https://power.vpnlabs.xyz/api/v1/keyword/${this.$route.params.id}`, config);
            this.contents = res.data.data;
            this.title = res.data.category.name;
            this.metacom = res.data.meta.comma;
            this.metadot = res.data.meta.dot;
            console.log(res.data);
        } catch (error) {
            console.log(error);
        }
    },
    head() {
        return {
            title: this.title + ' - ' + this.metadot ,
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
  .conts h3 {
    font-size: 20px;
    text-align: center;
  }
</style>