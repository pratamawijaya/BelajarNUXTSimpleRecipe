<template>
   <ul v-if="heroes && heroes.lenth">
      <li v-for="hero in heroes">
          <p>{{hero.name}}</p>
      </li>
   </ul>
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
            console.log(this.heroes)
        })
        .catch(e => {
            this.errors.push(e)
        })
  }
}
</script>
