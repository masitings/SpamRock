<template>
  <div>
    <h3>Welcome to Home Design Ideas</h3>
  </div>
</template>

<script>

export default {
  head() {
        return {
            title: 'Welcome to Home Design',
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
  h3 {
    text-align: center;
  }
</style>