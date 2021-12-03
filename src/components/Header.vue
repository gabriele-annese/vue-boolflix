<template>
    <section>
        <header id="header">
            <nav class="navbar">
                <ul class="navigation-ctn">
                    <div class="brand">
                        <img src="../assets/gabflix.png" alt="logo">
                    </div>
                    <li v-for="(elNav, i) in navBar" :key=" `el-${i}`">
                        <a href="/">{{elNav}}</a>
                    </li>
                </ul>
            </nav>
            <form>
                  <div class="search-box">
                        <button type= "submit" @click.prevent="sendEmit" class="btn-search">
                            <i class="fas fa-search"></i>
                            </button>
                        <input type="text" class="input-search"  v-model.trim= "textMovies"
                            @keyup.enter="sendEmit" placeholder="cerca il tuo film">
                    </div>
                <!-- <div class="search-box">
                    <button type="submit" @click.prevent="sendEmit">
                        <i class="fas fa-search"></i>
                    </button>
                    <input type="text"
                            class="from-control"
                            placeholder="Type to Search..."
                            v-model.trim= "textMovies"
                            @keyup.enter="sendEmit"
                    >
                </div> -->
            </form>
        </header>
        <Billboard />
    </section>
</template>

<script>
import Billboard from './Billboard.vue'
export default {
name: 'Header',
components: {
    Billboard
  },
data(){
    return{
        textMovies: '',
        navBar: [
            'Home',
            'Tv Shows',
            'Movies',
            'New & Popular',
            'My list'
        ]
    }
},
methods:{
    sendEmit(){
        if(this.textMovies !== '') this.$emit("clickMovies", this.textMovies);
        this.textMovies = "";
    }
},
}
window.onscroll = function(){
    let value = window.pageYOffset;
    console.log(value)
    if(value >= 230){
        document.querySelector('#header').style.background = '#000';
    }
    else{
        document.querySelector('#header').style.background = 'transparent';
    }
}
</script>

<style lang="scss" scoped>
header{
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 35px;
    height: 68px;
    width: 100%;
    z-index: 4;
    position: fixed;
    background:transparent ;
    transition: all 1.2s;
    .brand{
        max-width: 92px;
        height: fit-content;
        img{
            width: 100%;
            height: 100%;
            object-fit: contain;
        }
    }
    .navigation-ctn{
        list-style: none;
        display: flex;
        align-items: center;
        color: #b3b3b3;
        li{
            margin-left: 1rem;
            a{
                cursor: pointer;
                font-size: 0.8rem;
                color: #b3b3b3;
                text-decoration: none;
                &:hover,
                &:focus{
                    color: #fff;
                }
            }
        }
    }
.search-box{
  width: fit-content;
  height: fit-content;
  position: relative;
}
.input-search{
  height: 50px;
  width: 50px;
  border-style: none;
  padding: 10px;
  font-size: 18px;
  letter-spacing: 2px;
  outline: none;
  border-radius: 25px;
  transition: all .5s ease-in-out;
  background-color: transparent;
  padding-right: 40px;
  color:#fff;
}
.input-search::placeholder{
  color:rgba(255,255,255,.5);
  font-size: 18px;
  letter-spacing: 2px;
  font-weight: 100;
}
.btn-search{
  width: 50px;
  height: 50px;
  border-style: none;
  font-size: 20px;
  font-weight: bold;
  outline: none;
  cursor: pointer;
  border-radius: 50%;
  position: absolute;
  right: 0px;
  color:#ffffff ;
  background-color:transparent;
  pointer-events: painted;  
}
.btn-search:focus ~ .input-search{
  width: 300px;
  border-radius: 0px;
  background-color: transparent;
  border-bottom:1px solid rgba(255,255,255,.5);
  transition: all 500ms cubic-bezier(0, 0.110, 0.35, 2);
}
.input-search:focus{
  width: 300px;
  border-radius: 0px;
  background-color: transparent;
  border-bottom:1px solid rgba(255,255,255,.5);
  transition: all 500ms cubic-bezier(0, 0.110, 0.35, 2)
}
}

</style>