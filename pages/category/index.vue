<template>
  <b-container class="bv-example-row conts">
    <b-row>
      <b-col md="12" class="mb-3">
        <h3>Category Collection</h3>
      </b-col>
      <Catlist v-for="catlist in catlists" :catlist="catlist.name" :uuid="catlist.uuid" />
    </b-row>
  </b-container>
</template>

<script>
import axios from 'axios';
import Catlist from '../../components/Catlist';

export default {
  components: {
    Catlist
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
          const res = await axios.get('https://power.vpnlabs.xyz/api/v1/campaign/'+ process.env.campaignid +'/category/wallpaper', config);
          this.catlists = res.data;
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
  .conts h3 {
    font-size: 20px;
    text-align: center;
  }
</style>