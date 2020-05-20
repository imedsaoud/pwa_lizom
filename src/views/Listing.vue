<template>
  <div class="listing">
    <header class="home-header">
          <h1 class="home-brand">Fit Job</h1>
          <img class="home-first-background" src="../assets/background/home2.png" alt="">
    </header>
    <form class="home-form" action="">
      <input class="home-form-input-search" placeholder='Mot-clés ...' type="search">
        <div class="home-form-selects">
          <select name="contrat" id="select">
            <option value="Contrats">Contrat</option>
            <option value="cdi">CDI</option>
            <option value="cdd">CDD</option>
            <option value="free-lance">Free-lance</option>
            <option value="etudiant">Etudiant</option>
          </select>
          <select name="ville" id="select">
            <option value="paris">Paris</option>
            <option value="lyon">Lyon</option>
            <option value="marseille">Marseille</option>
            <option value="avignon">Avignon</option>
            <option value="toulouse">Toulouse</option>
            <option value="lille">Lille</option>
          </select>
        </div>
    </form>  
    
    <section class="profils">
      <h1 class="listing-title">Plus de {{profils.length}} candidats vous attendent !</h1>
      <div class="cards-wrapper">
        <div class="listing-card" v-for="profil in profils" :key="profil.id">
          <router-link :to="`/article/${profil.id}`" class="card-wrapper">
              <img class="card-description-avatar" src="../assets/avatars/user0.png" alt="">
              <div class="card-description">
                <div class="card-description-name">{{profil.nom}} {{profil.prenom}}</div>
                <div class="card-description-work">{{profil.poste}}</div>
                <div class="card-description-contract">{{profil.typeContrat}}</div>
                <span class="card-description-contract">{{profil.ville}}</span>
              </div>
          </router-link>
          <div>
            <router-link :to="`/article/${profil.id}`"><button class="button-consult">Consulter le profil</button></router-link>
            <button class="button-contact">Contacter dès maintenant</button>
          </div>
        </div>
      </div>

    </section>
    
  </div>
</template>

<script>
import profils from '../data/profils.json';
export default {

  data() {
    return{
      profils: profils
    }
  },
  created() {
    console.log('hello');
    
  }
}
</script>

<style scoped>

.listing {
  background-color: #FBFFFE;
}
  a {
    text-decoration: none;
  }
  .home-header {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
        overflow: hidden;
  }

  .home-brand {
    font-family: Futura;
    font-size: 21px;
    line-height: 25px;
    color: #FFFFFF;
    position: absolute;
    top: 1vh;
    width: 100%;
    text-align: center;
  }

  .home-first-background {
    height: 19vh;

  }

  .home-form {
    padding: 8vw 8vw 0 8vw;

  }

  .home-form-input-search {
    width: 100%;
    font-family: Futura;
    font-size: 14px;
    line-height: 16px;
    color: #A0A0A0 !important;
    border: 0.5px solid #EFEFEF;
    height: 6vh;
    padding: 6px;
    margin-bottom: 3vh;
}

.listing-card {
    display: flex;
    padding: 16px;
    background: #FFFFFF;
    border-radius: 3px;
    box-shadow: 0 3px 6px rgba(145, 145, 145, 0.16), 0 3px 6px rgba(161, 161, 161, 0.23);
    flex-direction: column;
}
.card-wrapper {
    display: flex;
    background: #FFFFFF;
}


.card-description {
  text-align: left;
  display: flex;
  justify-content: space-between;
  flex-direction: column;
}

.card-description-avatar {
  padding-right: 8vw;
}

.card-description-name {
  font-size: 16px;
  font-weight: 100;
  line-height: 19px;
  color: #282828;
}

.card-description-work {
  font-family: Futura;
  font-size: 16px;
  line-height: 19px;
  color: #282828;
}

.card-description-contract {
  font-size: 16px;
  line-height: 19px;
  color: #282828;
}

.card-description-contract {
  font-size: 16px;
  line-height: 19px;
  color: #282828;
}

.home-form-input-search ::placeholder {
  padding-left: 5px;
}

.home-form-selects {
  display: flex;
  width: 100%;
  justify-content: space-between;
}

#select {
  width: 48%;
  font-family: Futura;
  font-size: 14px;
  line-height: 16px;
  color: #A0A0A0;
  border: 0.5px solid #EFEFEF;
  border-radius: 2px;
  background-color: transparent;
  height: 6vh;
  margin-bottom: 3vh;
}

.listing-title {
  font-family: Futura;
  font-size: 17px;
  line-height: 28px;
  color: #3232AF;
  text-align: left;
 padding-bottom: 3vh;
}

.cards-wrapper {
  display: grid;
  grid-template-columns: 1fr;
  gap: 5vh;
  
}
.profils {
  padding:8vw;
}

.button-consult {
    display: none;
}

.button-contact {
    display: none;
}




@media (min-width: 1000px) { 

  .home-form {
    padding: 3vw 18vw 0 18vw;
  }
  .cards-wrapper {
    grid-template-columns: 1fr 1fr ;
    gap: 4vw 4vh;
  }

  .card-wrapper {
    padding-bottom: 3vh;
  }

  .button-consult {
    display: inline;
    width: 100%;
    background: #3232AF;
    box-shadow: 0px 4px 10px rgba(141, 151, 238, 0.15);
    border-radius: 2px;
    padding: 16px 79px;
    font-family: Futura;
    font-size: 14px;
    line-height: 16px;
    color: #FFFFFF;
    margin-bottom: 1vh;
  }

  .card-description-avatar {
    padding-right: 2vw;
  }

  .button-contact {
    display: inline;
    width: 100%;
    box-shadow: 0px 4px 10px rgba(141, 151, 238, 0.15);
    border-radius: 2px;
    color: #3232AF;
    border: 1px solid #3232AF;
    box-shadow: 0px 2px 2px rgba(140, 140, 140, 0.08);
    border-radius: 2px;
    padding: 14px 54px;
    font-family: Futura;
    font-size: 14px;
    line-height: 16px;
  }

  .listing-title {
    font-family: Futura;
    font-size: 36px;
    line-height: 42px;
    color: #3232AF;
  }


  .profils {
    padding: 0vw 18vw 0 18vw;
  }

  .card-description-name {
    font-size: 18px;
    line-height: 21px;
    color: #282828;
  }
    .card-description-work {
    font-family: Futura;
    font-size: 18px;
    line-height: 21px;
    color: #282828;
  }

   .home-brand {
      font-family: Futura;
      font-size: 45px;
      line-height: 25px;
      color: #FFFFFF;
      position: absolute;
      top: 0.5vh;
      width: 100%;
      text-align: center;
  }

 }

</style>