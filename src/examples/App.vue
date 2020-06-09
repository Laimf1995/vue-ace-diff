<template>
  <div>
    <JSON :leftContent='{}' :rightContent='{}' />
  </div>
</template>

<script>
import JSON from './JSON.js'

export default {
  name: 'app',
  components: {
    JSON
  },
  data () {
    return {
      leftContent: '{}',
      rightContent: '{}'
    }
  }
}
</script>

<style lang="scss">
@import '~ace-diffy/dist/ace-diffy-light.css';

.acediffy__container {
  width: 700px;
  height: 200px;
  margin: 2rem auto;
  position: relative;
}
</style>
