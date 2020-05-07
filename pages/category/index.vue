<template>
  <div>
    <h3>Categories</h3>
    <Content v-for="content in contents" :key="content.uuid" :id="content.uuid" :content="content.name" />
  </div>
</template>

<script>
import axios from 'axios';
import Content from '../../components/Content';

export default {
    components: {
        Content
    },
    data() {
        return {
            contents: []
        }
    },
    async created() {
        const config = {
            headers: {
                'Accept': 'application/json'
            }
        }

        try {
            const res = await axios.get('https://power.vpnlabs.xyz/api/v1/campaign/d4f2f638-5581-423a-8888-433617fbc155/category/wallpaper', config);
            this.contents = res.data;
            console.log(res.data);
        } catch (error) {
            console.log(error);
        }
    },
    head() {
        return {
            title: 'Category Page',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'this is meta description'
                }
            ]
        }
    }
}
</script>

<style>
    h3{
        text-align: center;
    }
</style>