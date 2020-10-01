<template>
  <div id="app">
    <div class="container grid-sm py-2">
      <img class="baner" src="https://picsum.photos/650" alt="Imagem baner">
      
      <div class="bemVindo">
        <spam class="subTitle"> Vida Toda </spam>
        <h1 class="title"> Bem Estar </h1>
        <spam class="text"> Soluções completas para viver mais e melhor </spam>

        <button class="buttonBemVindo"> Quero uma consultoria </button>
      </div>

      <div class="formBemVindo">
        <spam class="titleForm"> Pronto para planejar seu sossego? </spam>
        <spam class="subTitleForm"> Agende uma consultoria sem compromisso pelo formulário abaixo! </spam>

        <form
          id="formPlano"
          @submit="checkForm"
          action="#"
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
        <div class="noticia">
          <img class="imagemNoticia" src="https://picsum.photos/650" alt="imagem Noticia">
          <spam class="titleNoticia"> Entenda mais sobre o crescimento do marketing digital no Brasil </spam>
          <spam class="textNoticia"> De acordo com o IBGE, o número de pessoas que acessam a internet vem crescendo a cada dia. Já
            são mais de 100 milhões de pessoas conectadas no Brasil, considerand... </spam>

          <div class="buttonNoticia">
            <button class="buttonContinua"> Continuar </button>
          </div>
        </div>
        <div class="noticia">
          <img class="imagemNoticia" src="https://picsum.photos/650" alt="imagem Noticia">
          <spam class="titleNoticia"> Entenda mais sobre o crescimento do marketing digital no Brasil </spam>
          <spam class="textNoticia"> De acordo com o IBGE, o número de pessoas que acessam a internet vem crescendo a cada dia. Já
            são mais de 100 milhões de pessoas conectadas no Brasil, considerand... </spam>
          
          <div class="buttonNoticia">
            <button class="buttonContinua"> Continuar </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
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
  }
  .noticia:first-child{
    margin-right: 17px;
  }

  .noticia{
    border: 2px solid #292f6a;
    display: flex;
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
</style>
