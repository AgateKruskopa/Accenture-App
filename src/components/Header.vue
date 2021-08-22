//template
<template>
    <header>
        <img id="logo" alt="Vue logo" src="../assets/AA_logo.jpg">
        <ul id="nav">
            <li><a href="/" target="_blank">Home</a></li>
            <li><a href="/" target="_blank">All posts</a></li>
        </ul>
        <div class="button-container">
            <button id="plus-btn"
                v-on:click="clicker"
                >Add new post</button>
            <button
                id="user-btn"
                v-on:click="clicker"
                >Log in/Register</button>
        </div>
        <Dropdown :options="options" v-if="dropdownState"/>
    </header>
</template>

//script
<script>
    import Dropdown from './Dropdown.vue'

    export default {
        name: 'Header',
        props: {},
        data () {
            return {
                options: [
                    {
                        title: "Add new post",
                        url: "my-posts"
                    },
                    {
                        title: "Log in",
                        url: "login"
                    }
                ],
                dropdownState: false
            }
        },
        components: {
            Dropdown
        },
        methods: {
         clicker () {
            return this.dropdownState = !this.dropdownState
        }
        }     
    }
</script>

//style
<style>

@import url('https://fonts.googleapis.com/css2?family=Comfortaa:wght@400;700&display=swap');
    header {
        display: flex;
        background-color: #bb8760;
        width: 100%;
        justify-content: space-between;
    }

    #nav {
        display: flex;
        flex: 1;
        justify-content: start;
        list-style: none;
        
    }

    #nav > li {
        margin: 1rem 0rem;
    }

    #logo {
       margin: 10px 30px;
        width: 3.5rem;
        height: 4.5rem;
    }

    .button-container {
        display: flex;
    }

    #plus-btn, #user-btn, a {
        background-color: #bb8760;
        font-family: 'Comfortaa', cursive;
        color:#4f0e0e;
        position: relative;
        border: none;
        margin: 10px 10px; 
        text-decoration: none;
        font-size: 1rem;
    }


</style>

