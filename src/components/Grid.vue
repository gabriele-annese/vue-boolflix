<template>
    <section>
        <div class="list-movies"  v-if = "moviesArray !== null">
            <div v-for="(elMovies, index) in moviesArray" :key="`elMovies-${index}`" >
                <Card 
                :title="elMovies.title"
                :originalTitle="elMovies.original_title"
                :language="elMovies.original_language"
                :text="elMovies.vote_average"
                />
            </div>
        </div>
        <Loader v-else/>
    </section>
</template>

<script>
import Card from './Card.vue'
import Loader from './Loader.vue'
export default {
  components: { Card, Loader },
name: 'Grid',
props:{
    moviesArray: Array
}
}
</script>

<style lang="scss" scoped>

</style>