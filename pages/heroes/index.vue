<template>
    <ul v-if="heroes && heroes.length">
        <section class="heroes">
            <Hero
                v-for="hero in heroes"
                :key="hero.id"
                :img="hero.url_full_portrait"
                :name="hero.localized_name"
                :id="hero.id"
            />
        </section>
    </ul>
</template>

<script>
import Hero from '@/components/Hero'
import axios from 'axios';
export default {
    components : {
        Hero
    },
    asyncData(){
        return axios.get('https://raw.githubusercontent.com/joshuaduffy/dota2api/master/dota2api/ref/heroes.json')
        .then((res) => {
            return {
                heroes : res.data.heroes
            }
        })
        .catch(e => {
            return {
                error: e
            }
        })
    }
}
</script>

<style scoped>
    .heroes {
        display: flex;
        flex-flow: row wrap;
        justify-content: center;
        align-items: center;
    }
</style>
