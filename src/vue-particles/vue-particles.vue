<template>
  <div
    class="particles-js"
    :id="id"
    :config="config"
  ></div>
</template>
<script>
  /* eslint-disable */
  export default {
    name: 'vue-particles',
    data: function () {
      return {
        id: 'particles-instance-' + Math.floor(Math.random() * 5000)
      }
    },
    props: {
      config: {
        type: Object,
        default: null
      }
    },
    mounted () {
      // import particle.js only on client-side
      require('particles.js')
      this.$nextTick(() => {
        this.initParticleJS(this.config)
      })
    },
    methods: {
      initParticleJS (config) {
        particlesJS(this.id, config)
      }
    }
  }
  /* eslint-disable */
</script>
