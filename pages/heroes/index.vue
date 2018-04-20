<template>
    <h1>hello</h1>
</template>

<script>
import axios from 'axios';
import Hero from '@/components/Hero';
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
      axios.get('https://api.opendota.com/api/heroes')
        .then(response => {
            this.heroes = response.data
            // console.log(this.heroes)

            for(var hero in response.data){
                console.log(hero.localized_name)
            }
        })
        .catch(e => {
            this.errors.push(e)
        })
  }
}
</script>
