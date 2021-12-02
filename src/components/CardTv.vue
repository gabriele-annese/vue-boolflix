<template>
    <div class="container">
        <ul>
            <li class="content">
                <div class="cover">
                    <div >
                        <img class="movieImg" :src="`https://image.tmdb.org/t/p/w342${imgPoster}`" alt="cover_image" />
                    </div>
                </div>
                <div class="text">
                    <div class="text-overlay">
                        <div class="title">Titolo:{{ title }}</div>
                        <div class="orginalTitle">Titolo Originale: {{ originalTitle }}</div>
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
                    filter: brightness(13%);
                }
            }
        }
        .cover{
            margin-right: 10px;
            width: 100%;
            img{
                height: 450px;
            }
        }
        .text{
            position: absolute;
            top: 0;
            visibility: hidden;
            padding-left: 3px;
            padding-top: 100px;
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