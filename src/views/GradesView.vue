//    がんばれ!  🌻

<template>
    <main>
        <GameCard :name="this.name"
                  :date="this.date"
                  :rate="this.rate"
                  :image="this.image"
                  :platforms="this.platforms" />
    </main>
</template>

<script>

import GameCard  from '@/components/GameCard.vue';

export default {
    name: 'grades-view',
    props: {
        id:{
            type: String,
            required: true
        }
    },
    data: function(){
        return {
            name:"",
            platforms:[],
            date:"",
            rate: 0,
            image:""
        }
    },
    // computed: {},
    methods: {
        async fetchGame(){
            try{
                const response = await fetch("https://api.rawg.io/api/games/"+this.id+"?key=b730c728f6124b9dba5cf40a312f0f57")

                if (!response.ok){
                    if (response.status===404){
                        alert(`Game not found.`)
                        return
                    }
                    else {
                        throw new Error(`HTTP Error`+response.status)
                    }
                }

                const json = await response.json()

                console.log(json)

                this.name=json.name
                this.date=json.released
                this.rate=json.rating
                this.image=json.background_image

                json.parent_platforms.forEach((game)=>{
                    game.platform.name
                    // console.log(game.platform.name)
                    this.platforms.push(game.platform.name)
                })

            } catch (error) {
                console.log(error)
            }
        }
    },
    // watch: {},
    components: {
        GameCard
    },
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    created(){
        this.fetchGame()
    }
    // -- End Lifecycle Methods
}

</script>

<style scoped>
    
</style>