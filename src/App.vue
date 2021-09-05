<template>
    <input type="text" v-model="q">
    <button @click="fetchMovies">Submit</button>

    <div>
        <div v-for="(movie,index) in movies" :key="index">
            {{ movie.title }}
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            q: null,
            movies: []
        }
    },

    methods: {
        fetchMovies() {
            // fetch(`https://jsonplaceholder.typicode.com/posts?search=${this.q}`)
            let promise = fetch('https://jsonplaceholder.typicode.com/posts?search')

            let jsonPromise = promise.then(function (response) {
                return response.json()
            })

            // jsonPromise.then(function (jsonData) {
            //     that.movies = jsonData
            // })

            jsonPromise.then((jsonData) => {
                this.movies = jsonData
            })

        }
    }
}
</script>
