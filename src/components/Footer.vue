<template>
  <div class="FootersBox">
    <Footer1 />
    <Footer2 />
  </div>
</template>

<script>
import Footer1 from './Footer1'
import Footer2 from './Footer2'
export default {
  components: {
    Footer1,
    Footer2
  }
}
</script>

<style lang="scss" scoped>
.FootersBox {
  background: #fff;
}
</style>