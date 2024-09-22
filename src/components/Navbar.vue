//    がんばれ!  🌻

<template>
    <nav>
        <img src="@/assets/lightIcon.png" alt="Icon">
        <router-link to="/"><i class="fa-solid fa-house"></i></router-link>
    </nav>
</template>

<script>
export default {
    name: 'navbar-comp',
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
    nav{
        height: 8vh;
        padding: 1vh 5vw;
        display: flex;
        justify-content: space-between;
        background: #be4c6d;
        align-items: center;
    }

    nav a {
        font-weight: bold;
        text-decoration: none;
        color: #f394b2;
    }

    nav a.router-link-exact-active {
        color: #f9ecf1;
    }

    nav img{
        height: 90%;
    }
</style>