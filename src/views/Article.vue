<template>
  <div class="profil">
    <header class="home-header">
      <h1 class="home-brand">Fit Job</h1>
      <img class="home-first-background" src="../assets/background/home2.png" alt />
    </header>
    <section class="profil-description">
      <div class="profil-description-block1">
        <img class="profil-img" src="../assets/avatars/user0.png" alt />
        <div class="card-description">
            <div class="card-description-name">{{profil.nom}} {{profil.prenom}}</div>
            <div class="card-description-work">{{profil.poste}}</div>
            <div class="card-description-contract">{{profil.typeContrat}}</div>
            <span class="card-description-contract">{{profil.ville}}</span>
        </div>
      </div>
      <div class="profil-about">
        <h1 class="profil-about-title">À propos de {{profil.prenom}}</h1>
        <p class="profil-description-text">{{profil.description}}</p>
      </div>
      <div class="button-wrapper1"> 
        <button class="button1">Consulter le CV</button>
        <button class="button1">Consulter le portfolio</button>
      </div>
      <div class="contact-profil">
        <h1 class="contact-profil-title">Pour contacter ce candidat</h1>
        <div class="contact-profil-buttons">
          <button class="button2">E-mail</button>
          <button class="button2">Téléphone</button>
        </div>
        <router-link to="/listing/">
          <button class="button4">Consulter les autres profils</button>
        </router-link>
      </div>
    </section>
    <section class="aside-profil">
      <h1 class="aside-title">Profils similaires</h1>
      <div class="cards-wrapper">
           <div class="listing-card" v-for="profil in profils" :key="profil.id">
        <router-link :to="`/article/${profil.id}`" class="card-wrapper">
          <img class="card-description-avatar" src="../assets/avatars/user0.png" alt />
          <div class="card-description">
            <div class="card-description-name">{{profil.nom}} {{profil.prenom}}</div>
            <div class="card-description-work">{{profil.poste}}</div>
            <div class="card-description-contract">{{profil.typeContrat}}</div>
            <span class="card-description-contract">{{profil.ville}}</span>
          </div>
        </router-link>
        <div>
          <router-link :to="`/article/${profil.id}`">
            <button class="button3">Consulter le profil</button>
          </router-link>
          <button class="button3">Contacter dès maintenant</button>
        </div>
      </div>
      </div>
   
    </section>
  </div>
</template>



<script>
import profils from "../data/profils.json";
export default {
  data() {
    let profil = profils.find(profil => profil.id === this.$route.params.id);
    return {
      profil: profil,
      profils: profils
    };
  },
  created() {}
};
</script>

<style scoped>
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
  color: #ffffff;
  position: absolute;
  top: 1vh;
  width: 100%;
  text-align: center;
}

.home-first-background {
  height: 19vh;
}

.profil-description {
  display: grid;
  gap: 5vh;

}
.profil-description-block1 {
     padding-right: 8vw;
    padding-left: 8vw;
    padding-top: 4vh;
    display: flex;
    display: flex;
    justify-content: space-between;
    text-align: left;
}

.card-description {
  text-align: left;
  display: flex;
  justify-content: space-evenly;
  flex-direction: column;
}

.card-description-avatar {
  padding-right: 8vw;
  width: 27vw;
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

.profil-about-title {
  font-family: Futura;
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 21px;
  color: #282828;
  text-align: left;
}

.profil-about
 {
  padding-right: 8vw;
  padding-left: 8vw;
}

.profil-description-text {
  font-size: 14px;
  line-height: 140%;
  color: #000000;
  text-align: left;
  margin-bottom: 0;
}
.button-wrapper1 {
  padding: 0 8vw;
}

  .button1 {
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

  .button4 {
    background: #3FC494;
    box-shadow: 0px 4px 10px rgba(141, 151, 238, 0.15);
    border-radius: 2px;
    width: 100%;
    box-sizing: border-box;
    font-family: Futura;
    font-size: 14px;
    line-height: 16px;
    color: white;
    margin-bottom: 1vh;
    padding: 10px;
  }

  .contact-profil-title {
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 21px;
    color: #282828;
    text-align:left;
  }

  .button2 {
    width: 40%;
    border: 1px solid #3232AF;
    box-sizing: border-box;
    box-shadow: 0px 4px 10px rgba(141, 151, 238, 0.15);
    border-radius: 2px;
    font-family: Futura;
    font-size: 14px;
    line-height: 16px;
    color: #3232AF;
    background: white;
    margin-bottom: 1vh;
  }

  .contact-profil {
    padding: 0 8vw;
  }
  .contact-profil-buttons {
    display: flex;
    justify-content: space-between;
    padding-bottom: 5vh;
  }

  .button3 {
    display: none;
  }

  .listing-card {
    display: flex;
    padding: 16px;
    background: #FFFFFF;
    border-radius: 3px;
    box-shadow: 0 3px 6px rgba(145, 145, 145, 0.16), 0 3px 6px rgba(161, 161, 161, 0.23);
    flex-direction: column;
  }

  .aside-title {
    color:#3232AF;
    text-align: left;
    font-family: Futura;
    font-size: 24px;
    line-height: 28px;
  }

  .aside-profil {
    padding: 8vw;
  }

  .card-wrapper {
    display: flex;
  }

  .cards-wrapper {
    display: grid;
    grid-template-columns: 1fr;
    gap: 5vh;
  }

  @media (min-width: 1000px) { 
  

  .profil-description {
    padding: 4vh 14vw 0 ;
  }

  .profil-img {
    height: 15vw;
  }
  .cards-wrapper {
    grid-template-columns: 1fr 1fr ;
    gap: 4vw 4vh;
  }

  .card-wrapper {
    padding-bottom: 3vh;
  }

  .button2 {
    padding: 10px;
  }


  .profil-description-block1 {
    justify-content: initial;
  }

  .profil-img {
    margin-right: 3vw;
  }

  .card-description-avatar {
    padding-right: 2vw;
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
  .card-description-avatar {
    padding-right: 8vw;
    width: 10vw;
  }


 }
</style>