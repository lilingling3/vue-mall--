<template>
  <div class="hello">
   <y-header></y-header>
   <y-footer></y-footer>
  </div>
</template>

<script>
import YHeader from '@/common/header'
import YFooter from '@/common/footer'
export default {
  name: 'hello',
  data () {
    return {}
  },
  components:{YHeader,YFooter}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
