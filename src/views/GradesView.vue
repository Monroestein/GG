//    がんばれ!  🌻

<template>
    <main>
        
        <div class="left">
            <img :src="background_image" alt="">
        </div>
        
        <div class="right">
            <h2>{{ this.name }}</h2>
            <h3>{{ released }}</h3>
        </div>
    </main>
</template>

<script>
export default {
    name: 'grades-view',
    props: {
        id:{
            type: Number,
            required: true
        },
        name:{
            type: String,
            required: true
        },
        background_image:{
            type: String
        },
        released:{
            type: String
        },
        rating:{
            type: Number
        },
        platforms:{
            name:{
                type: String,
            }
        }
    },
    data: function(){
        return {}
    },
    // computed: {},
    // methods: {}
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
}
</script>

<style scoped>
    
</style>