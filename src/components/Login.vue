<template>
<div id="login-container">
    
    <form v-on:submit.prevent>
        <h2>Log in</h2>
        <input type="text" placeholder="Name"/>
        <input class="password" type="password" placeholder="Password"/>
        <button @click="authType.callBack">{{ authType.title }}</button>
        <p id="signUp">If You are not registered please <a href="/" target="_self">Sign up!</a></p>
    </form>
</div>
</template>

<script>
    export default {
        name: 'Login',
        props: {
            authType: {
                title: String,
                callBack: Function
            }
        }
    }
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Comfortaa:wght@400;700&display=swap');

#login-container{
    color: #ffdada;
    display: flex;
    align-items: center;
    max-width: 60rem;
    height: 100%;
    flex-direction: row;
    margin: auto;
    justify-content: center;
    padding: 2rem 0;
}

.password{
    margin: 20px;
}

input{
    box-shadow: -2px 3px 5px 0px rgba(0,0,0,0.75);
        -webkit-box-shadow: -2px 3px 5px 0px rgba(0,0,0,0.75);
        -moz-box-shadow: -2px 3px 5px 0px rgba(0,0,0,0.75);
}
</style>