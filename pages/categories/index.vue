<template>
  <div id="categories-page" class="page-wrapper categories-page">
    <button class="button is-primary" @click="$refs.plan.load()">
      Subscribe To Newsletter
    </button>
    <model-obj
      height="1000"
      width="1000"
      ref="plan"
      src="https://cors-anywhere.herokuapp.com/https://firebasestorage.googleapis.com/v0/b/firstbot-a1ca0.appspot.com/o/eyeball.obj?alt=media&token=d2c1a893-c80c-43d1-85b4-b9c5e8a788f7"
      @on-load="onLoad"
    ></model-obj>
    <div id="container"></div>
  </div>
</template>
<script>
import { ModelObj } from 'vue-3d-model'
export default {
  components: { ModelObj },
  head() {
    return {
      title: `Categories | ${this.$siteConfig.siteName}`
    }
  },
  methods: {
    onLoad() {
      this.loading = false
    }
  },
  mounted() {
    console.log('Component has been created!')
    this.$refs.plan.load()
  }
}
</script>
