<template>
  <div>
    <CatList v-for="catlist in catlists" :key="catlist.slug" :uuid="$route.params.id" :slug="catlist.slug" :catlist="catlist.keyword" />
  </div>
</template>

<script>
import axios from 'axios';
import CatList from '../../../components/CatList';

export default {
  components: {
    CatList
  },
  data() {
    return {
      catlists: []
    }
  },
  async created() {
    const config = {
        headers: {
            'Accept': 'application/json'
        }
    }

    try {
        const res = await axios.get(`https://power.vpnlabs.xyz/api/v1/keyword/${this.$route.params.id}/100/done`, config);
        this.catlists = res.data.data;
        console.log(res.data.data);
    } catch (error) {
        console.log(error);
    }
  }
}
</script>

<style>

</style>