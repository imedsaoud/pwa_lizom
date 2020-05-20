<template>
  <div class="home">
    
     
    <header class="home-header">
          <h1 class="home-brand">Fit Job</h1>
          <img class="home-first-background" src="../assets/background/home2.png" alt="">
    </header>
    <main class="main">
      <section class="home-search">
        <h1 class="home-search-title">Choisissez directement les profils qui vous intéressent.</h1>
        <p class="home-search-description">Avec fitjob, ne postez plus d’offres d’emplois, consulter la liste de nos candidats en fonction de vos critères et entrez en contact uniquement avec les profils correspondant.</p>
        <form class="home-form" action="/listing">
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
          <router-link to="/listing">
            <input class="home-form-submit" type="submit" value="Rechercher un candidat">
          </router-link>
          <link rel="stylesheet" href="#form2">
        </form>   
      </section>
      <section class="home-description">
        <div class="home-description-wrapper">
          <h1 class="home-description-title">Plus de 25 000 profils</h1>
          <p class="home-description-text">Fitjob est une plateforme unique en France, elle révolutionne le système d’embauche. Nous vous proposons d’échanger les rôles...</p>
        </div>
        <div class="home-description-wrapper">
          <h2 class="home-description-subtitle">Une recherche plus efficace</h2>
          <p class="home-description-text">Avec Fitjob arrêtez d’écumer les sites de recherche d’emploi, il vous suffit de poster votre profil pour qu’une entreprise vous contact. Fini les demandes sans réponse chaque prise de contact sera une réelle oportunité. Plus de 78% des personnes ayant posté leurs profils ont été co,tacté par une entreprise. Ne perdez plus votre temps avec vos candidatures sans réponse, postez votre profil.</p>
        </div>
        <div class="home-description-wrapper">
          <h2 class="home-description-subtitle">Une recherche plus efficace</h2>
          <p class="home-description-text">Avec Fitjob arrêtez d’écumer les sites de recherche d’emploi, il vous suffit de poster votre profil pour qu’une entreprise vous contact. Fini les demandes sans réponse chaque prise de contact sera une réelle oportunité. Plus de 78% des personnes ayant posté leurs profils ont été co,tacté par une entreprise. Ne perdez plus votre temps avec vos candidatures sans réponse, postez votre profil.</p>
        </div>
      </section>

      
      <button class="add-profil">Ajouter votre profil !</button>
  
    </main>

    
  </div>
</template>

<script>

export default {
  name: 'Home',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>



.home-first-background {
  height: 19vh;
}

.home-search {
  padding: 0 8vw 8vw 8vw;
  margin-bottom: 10px;
  
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
  top: 3vh;
  width: 100%;
  text-align: center;
}


.home-search-title {
  font-family: Futura;
  font-size: 21px;
  line-height: 25px;
  color: #3232AF;
  text-align: left;
}

.home-search-description {
  font-size: 16px;
  line-height: 140%;
  color: #282828;
  text-align: left;
  margin-bottom: 4vh;

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

.home-form-submit {
  width: 100%;
  height: 7vh;
  background: #3232AF;
  box-shadow: 0px 4px 10px rgba(141, 151, 238, 0.15);
  border-radius: 2px;
  font-family: Futura;
  font-size: 14px;
  line-height: 16px;
  color: #FFFFFF;
}


a {
  color: #3232AF;
}

h1 {
  margin: 0;
}
.home-description-wrapper {
  padding-right: 8vw; 
  padding-left: 8vw;
}

.home-description-wrapper:first-child {
    padding-top: 8vw;
}
.home-description-wrapper:last-child {
    padding-bottom: 6vw;
}

.home-description {
  background: #3FC394;
}
.home-description-title {
  font-family: Futura;
  font-size: 24px;
  line-height: 28px;
  text-align: left;
  color: #FBFFFE;
}

.home-description-subtitle {
  font-family: Futura;
  font-style: normal;
  font-weight: 500;
  font-size: 19px;
  line-height: 25px;
  color: #FFFFFF;
  text-align: left;
}

.home-description-text {
  font-family: Futura;
  font-size: 16px;
  line-height: 140%;
  text-align: left;
  color: #FFFFFF;
}

.add-profil {
  width:85%;
  height: 7vh;
  background: #3232AF;
  box-shadow: 0px 4px 10px rgba(141, 151, 238, 0.15);
  border-radius: 2px;
  font-family: Futura;
  font-size: 14px;
  line-height: 16px;
  color: #FFFFFF;
  margin-top: 6vh;
  margin-bottom: 6vh;
}



@media (min-width: 1000px) { 

  .home-first-background {
    width: 100%;
  }
  .home-description-wrapper {
    padding-right: 15vw; 
    padding-left: 15vw;
  }

  .home-description-wrapper:first-child {
      padding-top: 4vh;
  }
  .home-description-wrapper:last-child {
      padding-bottom: 4vh;
  }

  .home-search {
    padding-top: 10vh;
    padding-right: 30vw;
    padding-left: 30vw;
  }
  .add-profil {
    width: 40%;
    margin-top: 6vh;
    margin-bottom: 6vh;
  }

   .home-brand {
      font-family: Futura;
      font-size: 45px;
      line-height: 25px;
      color: #FFFFFF;
      position: absolute;
      top: 3.5vh;
      width: 100%;
      text-align: center;
  }
 }
</style>
