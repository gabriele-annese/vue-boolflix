<template>
  <ul>
      <li>
          
      </li>
      <li>
            <h2>
                Nome serie: {{title}}
            </h2>
      </li>
      <li>
            <h4>
                Nome Originale: {{originalTitle}}
            </h4>
      </li>
      <li class="img-container">
          <h4>
              Lingua:
          </h4>
            <img v-if="flagVisible" :src="require(`../assets/${this.language}.png`)" :alt="language">
            <h4  v-else>
                {{language}}
            </h4>
      </li>
      <li>
            <h4>
                Valutazione: {{text}}
            </h4>
      </li>
  </ul>
</template>

<script>
export default {
name: 'CardTv',
props:{
    title: String,
    originalTitle: String,
    language: String,
    text: Number,
},
computed:{
    flagVisible(){
        let visible = false
        if(this.language === "it" || this.language === "it-IT") visible= true;
        if (this.language === "en-EN" || this.language === "en") visible= true
        return visible;
    },
}
}
</script>

<style lang="scss" scoped>
ul {
    margin-top: 20px;
    margin-left: 10px;
    display: flex;
    flex-direction: column;
    li{
        list-style: none;
    }
    h2,h4{
        padding-top: 8px;
    }
    .img-container{
       display: flex;
       align-items: center;
    }
    img{
        margin: 5px 8px;
        width: 50px;
        height: 30px;
    }
}
</style>