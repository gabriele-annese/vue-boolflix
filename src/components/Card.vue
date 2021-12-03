<template>
    <div class="container">
        <ul>
            <li class="content">
                <div class="cover">
                    <div>
                        <img v-if="imgPoster" class="movieImg" :src="`https://image.tmdb.org/t/p/w342${imgPoster}`" alt="cover_image" />
                         <img v-else class="movieImg size-not-found" :src="require('../assets/imgnotfound.jpg')" alt="cover_image" />
                    </div>
                </div>
                <div class="text">
                    <div class="text-overlay">
                        <div class="title">Titolo: <h4>{{ title }}</h4></div>
                        <div class="orginalTitle">Titolo Originale:<h4>{{ originalTitle }}</h4></div>
                        <div class="language">
                            <img v-if="flagVisible" :src="require(`../assets/${this.language}.png`)" :alt="language" />
                            <span v-else>{{ language }}</span>
                        </div>
                        <div class="stars">
                                <i class="fas fa-star iStar" v-for="(el, i) in starsNumber" :key=" `el-${i}`"></i>
                        </div>
                        <div class="overview" v-if="overview">
                            <p>Overview:  {{ overview }}</p>
                        </div>
                        <div class="overview" v-else>
                            <p>Overview: No overview</p>
                        </div>
                    </div>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
name: 'CardTv',
props:{
    title: String,
    originalTitle: String,
    language: String,
    text: Number,
    imgPoster: String,
    overview: String,
},
computed:{
    flagVisible(){
        let visible = false
        if(this.language === "it" || this.language === "it-IT") visible= true;
        if (this.language === "en-EN" || this.language === "en") visible= true
        return visible;
    },
    starsNumber(){
        return Math.ceil(this.text / 2)
    }
}
}
</script>

<style lang="scss" scoped>
.container{
    display: flex;
    cursor: pointer;
    margin-top: 1rem;
    h4{
        display: inline-block;
    }
    ul{
        list-style: none;
        .content{
            position: relative;
            overflow: hidden;
            &:hover{
                .text{
                    visibility: visible;
                }
                .movieImg{
                    transition: all 0.4s;
                    filter: brightness(15%);
                }
            }
        }
        .cover{
            margin-right: 10px;
            width: 100%;
            img{
                border-radius: 10px;
                height: 450px;
            }
            .size-not-found{
                width: 342px;
                object-fit: cover;
            }
        }
        .text{
            position: absolute;
            top: 10px;
            visibility: hidden;
            padding-left: 3px;
        }
        .stars{
            i{
                color: gold;
            }
        }
    }

    .language img{
        width: 50px;
        height: 30px;
    }
}

</style>

  