<template>
  <div class="Billboard">
      <div class="innerBillboard">
          <img src="../assets/heroGabflix.jpg" alt="">
      </div>
  </div>
</template>

<script>
export default {
name: 'Billboard'
}
</script>
<style lang="scss" scoped>
    .Billboard{
        background-color: yellow;
        position: relative;
        top: -68px;
        left: 0;
        right: 0;
        .innerBillboard{
            position: absolute;
            z-index: -1;
        }
    }
</style>