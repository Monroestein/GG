//    がんばれ!  🌻

<template>
    <div class="container">
        <div>
            <h4 id="alert" v-if="alert">This game hasn't been graded yet.</h4>
        </div>

        <div class="users_grades">
            <div class="grade" v-if="newGrade">
                <h4>@{{ username }}</h4>
                <h5 style="margin-bottom:8px;"><i class="fa-solid fa-star"></i> {{ grade }}</h5>
                <p>{{ comment }}</p>

                <div class="buttons">
                    <button>Edit</button>
                    <button>Delete</button>
                </div>

            </div>
        </div>

        <div class="addingGrade" v-if="formToAddGrade">
            <form>
                <label for="name">Username</label>
                <input type="text" id="name" autocomplete="off" v-model="username">

                <label for="">Grade</label>
                <input type="number" maxlength="1" v-model="grade">

                <label for="">Comments</label>
                <input type="text" v-model="comment" autocomplete="off">

                <button type="submit" @click.prevent="hideForm">Save</button>
            </form>
        </div>

        <button @click="showForm">Add grade</button>

    </div>
</template>

<script>
export default {
    name: 'grades-view',
    props: {},
    data: function(){
        return {
            username:"",
            grade:"",
            comment:"",
            formToAddGrade: false,
            newGrade: false,
            alert:true
        }
    },
    // computed: {},
    methods: {
        showForm(){
            this.formToAddGrade = true;
        },
        hideForm(){
            this.formToAddGrade = false;
            this.newGrade = true
            this.alert=false
        }
    },
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
}

</script>

<style scoped>

    h4{
        color: #daff72;
        margin: 1rem auto;
    }

    #alert{
        border: 1px solid #d9ff7265;
        width: 70%;
        border-radius: 5px;
        padding: .5rem;
    }

    .container{
        margin: 2rem auto;
        padding-bottom: 7rem;
        position: relative;
    }

    button{
        cursor: pointer;
        border: 1px solid #daff7250;
        background: transparent;
        color: #daff72;
        border-radius: 5px;
        padding: .2rem .8rem;
        transition: border 1s;
        margin: 0 .3rem;
    }

    button:hover{
        border: 1px solid #eaffaf;
    }

    .buttons{
        margin: 1.5rem auto .2rem auto ;
    }

    .users_grades{
        margin: 1rem auto;
        width: 80%;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        align-items: stretch;
        gap: 1rem;
    }

    .grade{
        border: 1px solid #d9ff725b;
        border-radius: 5px;
        padding: 0rem 1rem 1rem 1rem;
        width: 30%;
        min-width: 200px;
    }

    .addingGrade{
        margin: .5rem auto;
        width: 45%;
        border-radius: 5px;
        border: 1px solid #daff7230;
        height: fit-content;
    }

    form{
        padding: 2rem;
        color: #c7c7c7;
        display: flex;
        flex-direction: column;
        align-items: start;
        gap: .5rem;
        margin-bottom: 1rem;
    }

    input{
        width:100%;
        padding: .5rem;
        background: #222;
        border: 1px solid #d9ff723a;
        color: #d3d2d2;
    }
</style>