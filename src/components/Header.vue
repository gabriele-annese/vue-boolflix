<template>
  <form>
      <input type="text"
            class="from-control"
            placeholder="cerca il tuo film"
            v-model.trim= "textMovies"
      >
      <button type="submit" @click.prevent="sendEmit">
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
methods:{
    sendEmit(){
        if(this.textMovies !== '') this.$emit("clickMovies", this.textMovies);
        this.textMovies = "";
    }
},
}
</script>

<style lang="scss" scoped>

</style>