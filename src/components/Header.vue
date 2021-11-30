<template>
  <form>
      <input type="text"
            class="from-control"
            placeholder="cerca il tuo film"
            v-model.trim= "textMovies"
            @keyup.enter="sendEmit"
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
input{
    outline: none;
    padding: 5px 5px;
    &:focus{
        border: 2px solid #000;
    }
}
button{
    margin-left: 10px;
    padding: 5px 5px;
    background: none;
    border: 1px solid black;
    cursor: pointer;
    &:focus,
    &:hover{
        background: #000;
        color: #fff;
    }
}
</style>