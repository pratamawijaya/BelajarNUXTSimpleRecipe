<template>
    <v-app light>
        <v-toolbar app>
            <v-toolbar-side-icon></v-toolbar-side-icon>
            <v-toolbar-title>Dota Heroes</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn icon>
                <v-icon>search</v-icon>
            </v-btn>
        </v-toolbar>
        <v-content>
            <v-container fluid>
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
            </v-container>
        </v-content>
        
    </v-app>
</template>

<script>
import Hero from '@/components/Hero'
import axios from 'axios';
export default {
    components : {
        Hero
    },
    data () {
        return {
            heroes : [],
            errors : []
        }
    },
    created() {
        axios.get('https://raw.githubusercontent.com/joshuaduffy/dota2api/master/dota2api/ref/heroes.json')
            .then(response => {
                this.heroes = response.data.heroes
            })
            .catch(e => {
                this.errors.push(e)
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
