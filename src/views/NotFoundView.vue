//    がんばれ!  🌻

<template>
    <main>

        <h1><i class="fa-solid fa-exclamation"></i></h1>
        <h2>404</h2>
        <h4>Page Not Found</h4>
    </main>
</template>

<script>
export default {
    name: 'notFound-view',
    // props: {},
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
    main{
        margin: 5rem auto;
        color: transparent;
        background: rgb(170, 66, 95);
        background: linear-gradient(160deg, rgba(190,76,109,1) 27%, rgb(247, 139, 173) 100%);
        background-clip: text;
    }

    h1{
        font-size: 8rem;
    }

    h2{
        font-size: 4rem;
    }
    
</style>