<template>
  <div id="app">
    <div class="container grid-sm py-2">
      <img class="baner" src="https://picsum.photos/650" alt="Imagem baner">
      
      <div class="bemVindo">
        <spam class="subTitle"> Vida Toda </spam>
        <h1 class="title"> Bem Estar </h1>
        <spam class="text"> Soluções completas para viver mais e melhor </spam>

        <button class="buttonBemVindo" v-on:click="consultoria"> Quero uma consultoria </button>
      </div>

      <div class="formBemVindo">
        <spam class="titleForm"> Pronto para planejar seu sossego? </spam>
        <spam class="subTitleForm"> Agende uma consultoria sem compromisso pelo formulário abaixo! </spam>

        <form
          id="formPlano"
          @submit="checkForm"
          action=""
          method="post"
        >
        <p>
          <label>Nome:</label>
          <input
            id="name"
            v-model="name"
            type="text"
            name="name"
          >
        </p>
        <p>
          <label>E-mail:</label>
          <input
            id="email"
            v-model="email"
            type="text"
            name="email"
          >
        </p>
        <p>
          <label>Estado Civil:</label>
          <input
            id="estCivil"
            v-model="estCivil"
            type="text"
            name="estCivil"
          >
        </p>
        <p>
          <label>Profissão:</label>
          <input
            id="prof"
            v-model="prof"
            type="text"
            name="prof"
          >
        </p>

        <p>
          <label>Telefone/Whatsapp:</label>
          <input
            id="tel"
            v-model="tel"
            type="number"
            name="tel"
          >
        </p>
        <p>
          <label>Renda Mensal:</label>
          <input
            id="renMensal"
            v-model="renMensal"
            type="number"
            name="renMensal"
          >
        </p>

        <spam>
          <input
            type="submit"
            value="Enviar"
            class="buttonForm"
          >
        </spam>
        </form>
      </div>

      <div class="penseNisso">
        <spam class="titlePenseNisso"> Pense nisso.. </spam>

        <spam class="textPenseNisso"> O quanto o diagnóstico de uma doença grave, internação ou cirurgia inesperada pode afetar,
          hoje, sua vida pessoal e financeira? </spam>
      </div>
      <div class="blog">
        Blog
      </div>
      <div class="noticiasBlog">
        <div class="noticia" v-for="post of posts.slice(0, 10)" v-bind:key="post.id">
          <img class="imagemNoticia" src="https://picsum.photos/650" alt="imagem Noticia">
          <spam class="titleNoticia"> {{ post.title }} </spam>
          <spam class="textNoticia"> {{ post.body }} </spam>

          <div class="buttonNoticia">
            <button class="buttonContinua"> Continuar </button>
          </div>
        </div>
        
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  
  name: 'App',
  data() {
    return {
      posts: null,
      name: null,
      email: null,
      estCivil: null,
      prof: null,
      tel: null,
      renMensal: null,

    }
  },
  mounted () {
    var self = this
    axios.get('https://jsonplaceholder.typicode.com/posts')
    .then(response => {
      self.posts = response.data
    })
    .catch (e => {
      console.log(e);
    })
  },
  methods: {
    consultoria: function (event) {
      console.log(event);
    },
    checkForm: function (event) {
      console.log(event)
    }
  }
}
</script>

<style scoped>
  .container {
    font-family: 'Roboto', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    background-color: #FFF;
    height: 100%;
    
  }
  .bemVindo{
    margin-left: 55px;
    color: #323469;
    display: flex;
    flex-direction: column;
    top: 27%;
    position: absolute;
    border: 2px solid #292f6a;
    padding: 1em 1em 1em; 
    max-width:275px;
    text-align: left;

  }
  .subTitle{
    font-weight: 700;
    font-size: 19px;
  }
  .title{
    text-transform: uppercase;
    font-weight: 700;
    display: flex;
    font-size: 75px
  }
  .text{
    font-weight: 700;
    font-size: 19px;
    margin-top: 78px;
  }
  .buttonBemVindo{
    margin-top: 58px;
    height: 50px;
    width: 220px;
    margin-left: 4%;
    background-color: #ef962e;
    color: #FFF;
    border: none;
  }

  .formBemVindo{
    width: 240px;
    background-color: #323469;
    display: flex;
    flex-direction: column;
    top: 58%;
    position: absolute;
    padding: 0em 1em 1em;
    left: 50%;
    transform: translateX(20%);
    line-height: 19px;
  }
  .titleForm{
    color: #ffa21d;
    font-weight: 700;
    font-size: 20px;
    text-align: left;
    margin-top:30px;
  }
  .subTitleForm{
    color: #ffF;
    font-weight: 700;
    font-size: 14px;
    text-align: left;
    margin-top:20px
  }
  #formPlano{
    color: #FFF;
    font-weight: 700;
    margin-top:20px;
  }
  #formPlano p{
    margin: auto;
    text-align: left;
  }
  #formPlano p input{
    height: 25px;
    background-color: #7a7b9e;
    border: none;
  }
  .buttonForm{
    border-radius: 10px;
    width: 40%;
    margin-top: 20px;
    font-weight: 700;
    color: #FFF;
    background-color: #ef962e;
    border: none;
  }
  .penseNisso{
    max-width: 240px;
    margin-top: 175px;
    display: flex;
    flex-direction: column;
    text-align: left;
    margin-left: 80px;
  }
  .titlePenseNisso{
    color: #ef962e;
    font-weight: 700;
    font-size: 25px;
  }
  .textPenseNisso{
    color: #323469;
    font-weight: 700;
    font-size: 14px;
    text-align: justify;
  }
  .blog{
    background-color: #323469;
    color: #FFF;
    font-weight: 300;
    max-width:335px;
    display:flex;
    align-items: center;
    justify-content: center;
    width: 80%;
    height: 67px;
    font-size: 40px;
    margin-top: 20px;
  }

  .imagemNoticia{
    max-height: 277px;
    max-width: 290px;
  }
  .noticiasBlog{
    display: flex;
    padding: 2em 3em 1em;
    flex-direction: row;
    flex-wrap: wrap;
  }

  .noticia{
    border: 2px solid #292f6a;
    display: flex;
    margin-top: 15px;
    margin-right: 10px;
    flex: 0 0 50%;
    max-width: 48%;
    flex-direction: column;
   
  }
  .titleNoticia{
    color: #323469;
    font-weight: 700;
    font-size: 19px;
    text-align: left;
    padding: 1em 1em 0em;
  }
  .textNoticia{
    color: #323469;
    font-weight: 300;
    font-size: 17px;
    text-align: left;
    padding: 1em 1em 1em;
  }

  .buttonNoticia{
    background-color: #313365;
    height: 70px;
    margin-top: auto;
    border: 2px solid #292f6a;
    display: flex;
    justify-content: center;
    align-items: center;
    
  }
  .buttonContinua{
    border-radius: 10px;
    font-weight: 700;
    height: 40%;
    color: #FFF;
    background-color: #ef962e;
    border: none;
  }
  @media only screen and (max-width: 720px) and (min-width: 321px) {
    .baner {
      width: 100%;
    }
    .bemVindo{
      top: 3%;
    }
    .formBemVindo {
      position: unset;
      top: unset;
      margin-top: 60%;
      width: 275px;
      padding: 1em 2em 1em;
    }
    .penseNisso {
      margin-top: 15px;
    }
    .noticiasBlog {
      flex-direction: column;
      padding: 1em 1em 1em;
    }
    .noticia:first-child{
      margin-right: unset;
    }
    .noticia{
      margin-bottom: 10px;
      margin-top: 0;
      margin-right: 0;
      flex: none;
      max-width: none;
    }
    .imagemNoticia{
      max-width: 100%;
    }
  } 
  @media only screen and (max-width: 320px){
    .baner {
      width: 107%;
    }
    .bemVindo{
      top: 3%;
      margin-left: 15px;
    }
    .formBemVindo {
      position: unset;
      top: unset;
      margin-left: 15px;
      transform: unset;
      margin-top: 68%;
      width: 275px;
      padding: 1em 2em 1em;
    }
    .noticia{
      margin-top: 0;
      margin-right: 0;
      flex: none;
      max-width: none;
    }
  }
  @media only screen and (max-width: 900px) and (min-width: 720px){
     .baner {
      width: 100%;
    }
    .bemVindo{
      top: 21%;
      margin-left: 15px;
    }
    .formBemVindo {
      margin-left: 15px;
      position: absolute;
      top: 35%;
      transform: translateX(-1%);
      width: 275px;
      padding: 1em 2em 1em;
    }
    .penseNisso {
      margin-top: 21%;
      margin-left: 23px;
    }
  }
  @media only screen and (max-width: 1366px) and (min-width: 900px){
    .formBemVindo{
      top: 41%;
    }
  }
</style>
