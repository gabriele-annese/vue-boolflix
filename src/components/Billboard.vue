<template>
  <div class="Billboard">
      <div class="innerBillboard">
          <p>hello</p>
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
        top: 0;
        left: 0;
        right: 0;
        .innerBillboard{
            position: absolute;
        }
    }
</style>