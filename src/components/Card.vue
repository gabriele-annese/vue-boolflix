<template>
  <ul>
      <li>
            <h2>
                Titolo: {{title}}
            </h2>
            <h4>
                Titolo Originale: {{originalTitle}}
            </h4>
            <h4>
                Lingua: {{language}}
            </h4>
            <h4>
                Valutazione: {{text}}
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
ul {
    margin-top: 20px;
    margin-left: 10px;
    h2,h4{
        padding-top: 8px;
    }
}
</style>