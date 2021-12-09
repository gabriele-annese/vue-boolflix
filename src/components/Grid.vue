<template>
    <section>
        <div class="segment">
            <h3>Original netflix</h3>
                <div class="row">
                    <div class="slider">
                        <div v-for="(elMovies, index) in moviesArray" :key="`elMovies-${index}`" >
                                <Card 
                                :title="elMovies.title"
                                :originalTitle="elMovies.original_title"
                                :language="elMovies.original_language"
                                :text="elMovies.vote_average"
                                :imgPoster="elMovies.poster_path"
                                :overview="elMovies.overview"
                                />
                        </div>
                    </div>
                </div>
        </div>
            <!-- series -->
            <div class="segment" >
                <h3>Series</h3>
                <div class="row">
                    <div class="slider">
                        <div v-for="(elTv, index) in tvArray" :key="`elTv-${index}`">
                            <CardTv
                            :title="elTv.name"
                            :originalTitle="elTv.original_name"
                            :language="elTv.original_language"
                            :text="elTv.vote_average"
                            :imgPoster="elTv.poster_path"
                            :overview="elTv.overview"
                            />
                    </div>

                </div>
                </div>
            </div>
    </section>
</template>

<script>
import Card from './Card.vue'
import CardTv from './CardTv.vue'
export default {
  components: { Card, CardTv },
name: 'Grid',
props:{
    moviesArray: Array,
    tvArray: Array,
    top10Movies: Array
},
data(){
    return{
        Imgsize: 'w342'
    }
},
}
</script>

<style lang="scss" scoped>
.segment{
    margin: 0 auto;
	padding: 1rem;
	font-size: 1rem;
	line-height: 1.5rem;
    h3{
        color: #e5e5e5;
        font-weight: bold;
        font-size: 1.3rem;
    }
    .row{
        display: flex;
		overflow: hidden;
		align-items: center;
        .slider{
            width: 100%;
			display: flex;
			flex-shrink: 0;
			overflow-x: auto;
			scrollbar-width: thin;
        }
    }
}
</style>