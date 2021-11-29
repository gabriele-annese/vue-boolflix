<template>
  <form>
      <input type="text"
            class="from-control"
            placeholder="cerca il tuo film"
            v-model= "textMovies"
      >
      <button class="submit">
          search
      </button>
  </form>
</template>

<script>
export default {
name: 'Header',
data(){
    return{
        textMovies: ''
    }
},
}
</script>

<style lang="scss" scoped>

</style>