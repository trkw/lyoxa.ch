<template>
  <section class="container">
    <h1>Contact</h1>

    <h2>Nouvelle demande</h2>
    <div class="row">
      <div class="col">
        <p class="lead">Merci de nous faire parvenir toutes vos demandes via le <nuxt-link to="/formulaire-de-demande/">formulaire de demande</nuxt-link>.</p>
        <nuxt-link class="btn btn-primary btn-lg" to="/formulaire-de-demande/" role="button">Formulaire de demande</nuxt-link>
      </div>
    </div>

    <h2 class="mt-5">Association Lyoxa</h2>
    <div class="row">
      <div class="col-lg-6">
        <team
          name="Association Lyoxa"
          photo="/img/logo.svg"
          postal-code="CH-1200" locality="Genève"
          email="info@lyoxa.ch">
        </team>
      </div>
    </div>

    <h2 class="mt-5">Équipe</h2>
    <div class="row">
      <div class="col-lg-6">
        <team
          class="mb-5 mb-md-0"
          name="Nicolas Tamayo Lopez"
          title="Président"
          photo="/img/equipe/tamayo-lopez-nicolas.jpg"
          address="Chemin des Marettes 1" postal-code="CH-1293" locality="Bellevue"
          email="nicolas.tamayo.lopez@lyoxa.ch"
          phone="+41 76 200 64 26">
        </team>
      </div>
      <div class="col-lg-6">
        <team
          class="mb-5 mb-md-0"
          name="Célia Sepe"
          title="Secrétaire Générale"
          photo="/img/equipe/sepe-celia.jpg"
          address="Rue Louis-Favre 31" postal-code="CH-1201" locality="Genève"
          email="celia.sepe@lyoxa.ch"
          phone="+41 79 226 37 78">
        </team>
      </div>
      <div class="col-lg-6">
        <team
          class="mb-5 mb-md-0"
          name="Stéphanie Catterson"
          title="Trésorière"
          photo="/img/equipe/catterson-stephanie.jpg"
          address="Route de St-Cergue 22" postal-code="CH-1273" locality="Arzier"
          email="stephanie.catterson@lyoxa.ch"
          phone="+41 79 710 05 27">
        </team>
      </div>
      <div class="col-lg-6">
        <team
          class="mb-5 mb-md-0"
          name="Thibaud Mabut"
          title="Délégué à la communication"
          photo="/img/equipe/mabut-thibaud.jpg"
          address="Rampe du Pont-Rouge 7a" postal-code="CH-1213" locality="Petit-Lancy"
          email="thibaud.mabut@lyoxa.ch"
          phone="+41 76 375 81 56">
        </team>
      </div>
      <div class="col-lg-6">
        <team
          class="mb-5 mb-md-0"
          name="Marc Delacrétaz"
          title="Délégué à la logistique"
          photo="/img/equipe/delacretaz-marc.jpg"
          address="Chemin de la Menuiserie 31" postal-code="CH-1293" locality="Bellevue"
          email="marc.delacretaz@lyoxa.ch"
          phone="+41 79 580 32 42">
        </team>
      </div>
      <div class="col-lg-6">
        <team
          class="mb-5 mb-md-0"
          name="Louis Mégroz"
          title="Délégué aux infrastructures"
          photo="/img/equipe/megroz-louis.jpg"
          address="Passage Daniel Baud-Bovy 10" postal-code="CH-1205" locality="Genève"
          email="louis.megroz@lyoxa.ch"
          phone="+41 76 343 60 74">
        </team>
      </div>
      <div class="col-lg-6">
        <team
          class="mb-5 mb-md-0"
          name="Guillaume Tschuy"
          title="Délégué au service juridique"
          photo="/img/equipe/tschuy-guillaume.jpg"
          address="Chemin Ami-Argand 37" postal-code="CH-1290" locality="Versoix"
          email="guillaume.tschuy@lyoxa.ch"
          phone="+41 78 801 09 72">
        </team>
      </div>
      <div class="col-lg-6">
        <team
          class="mb-5 mb-md-0"
          name="Julien Grünhagel"
          title="Délégué IT"
          photo="/img/equipe/grunhagel-julien.jpg"
          address="26 avenue des Eidguenots" postal-code="CH-1203" locality="Genève"
          email="julien.grunhagel@lyoxa.ch"
          phone="+41 79 674 41 03">
        </team>
      </div>
      <div class="col-lg-6">
        <team
          class="mb-5 mb-md-0"
          name="Jules Lorenzi"
          title="Gestionnaire de dossiers"
          photo="/img/equipe/lorenzi-jules.jpg"
          address="Rue De L’Athénée 4" postal-code="CH-1205" locality="Genève"
          email="jules.lorenzi@lyoxa.ch"
          phone="+41 78 849 55 89">
        </team>
      </div>
      <div class="col-lg-6">
        <team
          class="mb-5 mb-md-0"
          name="Sophie Ratcliff"
          title="Gestionnaire de dossiers"
          photo="/img/equipe/ratcliff-sophie.jpg"
          address="Avenue Sainte-Cécile 27" postal-code="CH-1217" locality="Meyrin"
          email="sophie.ratcliff@lyoxa.ch"
          phone="+41 76 615 87 33">
        </team>
      </div>
      <div class="col-lg-6">
        <team
          class="mb-5 mb-md-0"
          name="Florian Parini"
          title="Gestionnaire de dossiers"
          photo="/img/equipe/parini-florian.jpg"
          address="Route De Thonon 214" postal-code="CH-1222" locality="Collonge-Bellerive"
          email="florian.parini@lyoxa.ch"
          phone="+41 79 721 27 25">
        </team>
      </div>
    </div>
  </section>
</template>

<script>
import Team from '~/components/Team'
export default {
  head () {
    return {
      title: 'Contact - Lyoxa',
      meta: [
        { hid: 'description', name: 'description', content: 'Contacter Lyoxa' },
        { property: 'og:url', content: 'https://lyoxa.ch/contact/', hid: 'og_url' },
        { property: 'og:title', content: 'Lyoxa - Contact', hid: 'og_title' },
        { property: 'og:description', content: 'Contacter Lyoxa', hid: 'og_description' }
      ]
    }
  },
  components: {
    Team
  }
}
</script>
