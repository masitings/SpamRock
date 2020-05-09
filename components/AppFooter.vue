<template>
  <div class="fluid-container footer">
    <p class="text-center">Copyright &copy 2020, {{sitename}}. All Rights Reserved.</p>
    <div class="link-footer">
        <nuxt-link :to="'/page/term-of-use'">Term of Use</nuxt-link>
        |
        <nuxt-link :to="'/page/privacy-policy'">Privacy Policy</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
    name: 'AppFooter',
    data(){
        return {
            sitename: '',
        }
    },
    async created() {
	    this.sitename = process.env.sitename;
   }
}
</script>

<style>
    .footer {
        margin-top: 20px;
        background: #6c757d;
        padding: 8px;
        color: white;
        position: static;
    }
    .link-footer{
        text-align: center;
    }
    .link-footer a {
        color: white;
    }
    .link-footer a:hover {
        text-decoration: none;
    }
    .footer p {
        margin-bottom: 0;
    }
</style>