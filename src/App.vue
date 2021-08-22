<template>
    <div>
    <Header/>
    <div class="page-container">
      <Article
      v-for="article in articleArray"
      :title="article.title"
      :img="article.img"
      :key="article.title"
      v-on:click="clicker"
      />
    </div>
    <NewArticle/>
    <Login :authType="authType" />
    <Registration/>
    <Footer/>
    </div>
</template>

<script>
import Header from './components/Header.vue'
import Article from './components/Article.vue'
import Login from './components/Login.vue'
import NewArticle from './components/NewArticle.vue'
import Registration from './components/Registration.vue'
import Footer from './components/Footer.vue'


export default {
  name: 'App',
  data () {
    return {
      articleArray: [
        {
          title: "Bordeaux wine glass",
          img: "https://images.crateandbarrel.com/is/image/Crate/ia-types-wine-glasses-5"
        },
        {
          title: "Burgundy wine glass",
          img: "https://images.crateandbarrel.com/is/image/Crate/ia-types-wine-glasses-7"
        },
        {
          title: "White wine glass",
          img: "https://images.crateandbarrel.com/is/image/Crate/ia-types-wine-glasses-11"
        }
      ], 

      footerArray: [
        {
          subscription: "Created by Agnija and Agate",
          logo: ""
        }
      ],
    
      authType: "/register"
    }
  },
  components: {
    Header,
    Article,
    Login,
    NewArticle,
    Registration,
    Footer
  },
  methods: {
    clicker () {
      console.log('clickerino works!')
    },
    submitFn () {
      console.log('logged in!')
    },
    authSwitcher () {
    const navUrl = "/register";

    if (navUrl === "/register") {
      return this.authType = {
        title: "Login",
        callBack: this.submitFn
      }
    }
}
  },
  mounted() {
    this.authSwitcher()
  }
}
</script>


//concept



<style>
@import url('https://fonts.googleapis.com/css2?family=Comfortaa:wght@400;700&display=swap');

  body {
    margin: 0;
    padding: 0;
    background-color: #4f0e0e;
    width: 100%;
    color:#bb8760;
  font-family: 'Comfortaa', cursive;
  }

  .page-container {
    height: 100%;
    display: flex;
    flex-direction: row;
    margin: 0 5rem;
    justify-content: space-between;
    align-items: center;
    padding: 3rem 0;
  }

  @media (max-width: 768px) {
    .page-container {
      flex-direction: column;
      align-items: center; 
    }
  }
</style>
