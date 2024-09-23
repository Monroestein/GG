//    がんばれ!  🌻

<template>
    <div class="container">

        <div class="left">
            <h1 class="name_mobile">{{ name }}</h1>
            <img :src="image" alt="">
        </div>

        <div class="right">
            <h1 class="name_desk">{{ name }}</h1>

            <h4>Released: {{ date }}</h4>
            
            <h5>{{ platforms }}</h5>

            <div class="rating">
                <i class="fa-solid fa-star"></i>
                <h2>{{ rate }}</h2>
            </div>

        </div>

    </div>
</template>

<script>
export default {
    name: 'gamecard-comp',
    props: {
        id:{
            type: Number,
            required: true
        },
        name:{
            type: String,
            required: true
        },
        image:{
            type: String,
            required: true
        },
        date:{
            type: String,
            required: true
        },
        platforms:{
            type: String,
            required: true
        },
        rate:{
            type: Number,
            required: true
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
    .container{
        width: 90%;
        margin: 2rem auto;
        padding: .5rem;
        display: flex;
        flex-direction: column;
        background: #be4c6d10;
    }

    .left{
        color: #d16f8b;
    }

    .right{
        line-height: 2rem;
    }

    img{
        width: 100%;
        margin: 1rem auto;
    }

    .rating{
        margin-top: 10px;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 1rem;
    }

    i{
        font-size: .8rem;
        margin-left: .5rem;
    }

    .name_desk{
        display: none;
    }

</style>