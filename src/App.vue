<template>
  <div>
    <Header @ganti-hero="gantiHero"></Header>
    <main>
      <p>Hero-hero terbaik minggu ini:</p>
        <article v-if="!selectedHero">
          <Hero v-for="(item, index) in hero" :hero="item" :index="index"></Hero>
        </article>
        <article v-else>
          <Hero :hero="selectedHero" :index="0"></Hero>
        </article>
    </main>
    <Footer></Footer>

  </div>

</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Hero from './components/Hero.vue'

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    Hero
  },
  data: function () {
    return {
      hero: [
        {
          id: 1,
          nama: 'Aurora',
          type: 'Mage',
          gambar: 'aurora.jpg'
        },
        {
          id: 2,
          nama: 'Zilong',
          type: 'Fighter',
          gambar: 'zilong.jpg'
        },
        {
          id: 3,
          nama: 'Akai',
          type: 'Tank',
          gambar: 'akai.jpg'
        },
        {
          id: 4,
          nama: 'Bruno',
          type: 'Marksman',
          gambar: 'bruno.jpg'
        },
        {
          id: 5,
          nama: 'Gatot Kaca',
          type: 'Tank',
          gambar: 'gatotkaca.png'
        },
        {
          id: 6,
          nama: 'Hilda',
          type: 'Tank',
          gambar: 'hilda.jpg'
        },
        {
          id: 7,
          nama: 'Lancelot',
          type: 'Assasin',
          gambar: 'lancelot.jpg'
        },
        {
          id: 8,
          nama: 'Lapu-lapu',
          type: 'Fighter',
          gambar: 'lapulapu.jpg'
        },
        {
          id: 9,
          nama: 'Layla',
          type: 'Marksman',
          gambar: 'layla.jpg'
        },
        {
          id: 10,
          nama: 'Lolita',
          type: 'Tank',
          gambar: 'lolita.jpg'
        },
        {
          id: 11,
          nama: 'Nana',
          type: 'Mage',
          gambar: 'nana.png'
        },
        {
          id: 12,
          nama: 'Roger',
          type: 'Marksman',
          gambar: 'roger.jpg'
        },
      ],
      selectedHero: ''
    }
  },

  methods: {
    gantiHero: function () {
      this.selectedHero = this.randomHero()
    },
    randomHero(){
      return this.hero[Math.floor(Math.random() * this.hero.length)]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

main img {
  width: 80px;
  border: solid 1px grey;
}

article{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

main{
  text-align: center;
}
</style>
