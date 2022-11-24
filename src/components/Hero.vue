<template>
    <div>
        <ul>
            <li>
                <img :src="gambar" alt="">
                <p>{{ index + 1 }} - {{ hero.nama }}</p>
                <p>Jenis hero: <u>{{ hero.type }}</u></p>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    computed: {
        gambar() {
            return require('../assets/hero/' + this.hero.gambar)
        }
    },
    props: ['hero', 'index'],

}
</script>

<style scoped>
p {
    /* 
   color: salmon;
   */
    margin: 0;
}

li {
    list-style: none;
}
</style>