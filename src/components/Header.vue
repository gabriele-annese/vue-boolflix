<template>
    <section>
        <header>
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
        background: #dc1a28;
        color: #fff;
    }
}
}
</style>