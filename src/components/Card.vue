<template>
    <div class="card">
    <ul>
        <li class="content">
            <div class="cover">
                <div>
                        <img v-if="imgPoster" :src="`https://image.tmdb.org/t/p/w342${imgPoster}`" :alt="{title}">
                        <div v-else>
                            <p>
                                non dispo
                            </p>
                        </div>
                </div>
            </div>
            <div class="info">
                <div class="info-overlay">
                    <div class="title">
                        <h2>
                            Titolo: {{title}}
                        </h2>
                    </div>
                    <div class="OriginalTitle">
                        <h4>
                            Titolo Originale: {{originalTitle}}
                        </h4>
                    </div>
                    <div class="language">
                        <h4>
                            Lingua:
                        </h4>
                        <img v-if="flagVisible" :src="require(`../assets/${this.language}.png`)" :alt="language">
                        <h4  v-else>
                            {{language}}
                        </h4>
                    </div>
                    <div class="starts">
                        <div class="stars-ctn">
                            <i class="fas fa-star iStar" v-for="(el, i) in starsNumber" :key=" `el-${i}`"></i>
                        </div>
                    </div>
                    <div class="overview">
                        <p>
                            {{overview}}
                        </p>
                    </div>
                </div>
            </div>
        </li>
    </ul>
    </div>
</template>

<script>
export default {
name: 'Card',
props:{
    imgPoster: String,
    title: String,
    originalTitle: String,
    language: String,
    text: Number,
    overview: String,
},
computed:{
    flagVisible(){
        let visible = false
        if(this.language === "it" || this.language === "it-IT") visible= true;
        if (this.language === "en-EN" || this.language === "en") visible= true;
        return visible;
    },
    starsNumber(){
        return Math.ceil(this.text / 2)
    },
},


}
</script>

<style lang="scss" scoped>
.card {
	display: flex;
	flex-shrink: 0;
	padding: 0.5rem;
	cursor: pointer;
	margin-top: 1rem;
	width: calc(100% / 6);
	flex-direction: column;
    ul{
        list-style: none;
        position: relative;
        .content{
            width: 100%;
            display: flex;
            align-items: center;
            .cover{
                width: 100%;
                height: 345px;
                overflow: hidden;
                position: relative;
                div:fist-of-type{
                    padding-bottom: calc(100% * 1);
                    img{
                        position: absolute;
                        top: 0;
                        width: 100%;
                        height: 100%;
                    }
                }
            }
        }
    }
}
</style>