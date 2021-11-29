<template>
  <ul>
      <li>
            <h2>
                {{title}}
            </h2>
            <h4>
                {{originalTitle}}
            </h4>
            <h4>
                {{language}}
            </h4>
            <h4>
                {{text}}
            </h4>
      </li>
  </ul>
</template>

<script>
export default {
name: 'Card',
props:{
    title: String,
    originalTitle: String,
    language: String,
    text: Number,
}
}
</script>

<style lang="scss" scoped>

</style>