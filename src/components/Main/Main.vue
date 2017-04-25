<template>
  <div>
    <h1>Liste des personnages</h1>
    <liste></liste>

  </div>
</template>

<script>
import Liste from '@/components/Liste/Liste'

export default {
  name: 'main',
  components: {
    liste: Liste
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1 {
    color: blue;
  }
</style>