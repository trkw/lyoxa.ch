<template>
  <div>
    <form v-on:submit.prevent="onSubmit" id="needs-validation" v-if="!formSubmittedSuccessfully && !errorAfterSubmission" novalidate>
      <p><span class="text-danger">*</span> = Champ requis</p>

      <div class="alert alert-danger" role="alert" v-if="formIsSubmitted && !formIsValid">
        Une/plusieurs erreur(s) est/sont présente(s) dans le formulaire; merci de la/les corriger.
      </div>

      <div class="form-row">
        <div class="form-group col-sm-6">
          <label for="contactInputFirstname">Prénom <span class="text-danger">*</span></label>
          <input type="text" class="form-control" id="contactInputFirstname" v-model="contact.firstName" required>
          <div class="invalid-feedback">
            Le prénom est requis
          </div>
        </div>
        <div class="form-group col-sm-6">
          <label for="contactInputName">Nom <span class="text-danger">*</span></label>
          <input class="form-control" id="contactInputName" v-model="contact.name" required>
          <div class="invalid-feedback">
            Le nom est requis
          </div>
        </div>
      </div>
      <div class="form-row">
        <div class="form-group col-sm-6">
          <label for="contactInputEmail">Adresse e-mail <span class="text-danger">*</span></label>
          <input type="email" class="form-control" id="contactInputEmail" v-model="contact.email" required>
          <div class="invalid-feedback">
            L'adresse e-mail est requise
          </div>
        </div>
        <div class="form-group col-sm-6">
          <label for="contactInputPhone">Numéro de téléphone <span class="text-danger">*</span></label>
          <input type="tel" class="form-control" id="contactInputPhone" v-model="contact.phone" required>
          <div class="invalid-feedback">
            Le numéro de téléphone est requis
          </div>
        </div>
      </div>
      <div class="form-group">
        <label for="contactInputAssociation">Nom de l'association/du collectif représenté</label>
        <input class="form-control" id="contactInputAssociation" v-model="contact.association">
      </div>
      <div class="form-group">
        <label for="contactInputDemand">Votre demande en détails <span class="text-danger">*</span></label>
        <textarea class="form-control" id="contactInputDemand" rows="8" cols="80" v-model="contact.demand" required></textarea>
        <div class="invalid-feedback">
          Le détail de votre demande est requis
        </div>
      </div>
      <div class="form-group">
        <label>Le type de service dont vous avez besoin <span class="text-danger">*</span></label>
        <div class="form-check">
          <label class="form-check-label">
            <input class="form-check-input" type="checkbox" v-model="contact.services.statusLegal">
            Statuts et légal
          </label>
        </div>
        <div class="form-check">
          <label class="form-check-label">
            <input class="form-check-input" type="checkbox" v-model="contact.services.budgets">
            Budgets, comptabilité et trésorerie
          </label>
        </div>
        <div class="form-check">
          <label class="form-check-label">
            <input class="form-check-input" type="checkbox" v-model="contact.services.teamManagement">
            Gestion d'équipe
          </label>
        </div>
        <div class="form-check">
          <label class="form-check-label">
            <input class="form-check-input" type="checkbox" v-model="contact.services.teamBuilding">
            Constitution d'équipe
          </label>
        </div>
        <div class="form-check">
          <label class="form-check-label">
            <input class="form-check-input" type="checkbox" v-model="contact.services.communicationDesign">
            Communication et Webdesign
          </label>
        </div>
        <div class="form-check">
          <label class="form-check-label">
            <input class="form-check-input" type="checkbox" v-model="contact.services.autorisations">
            Autorisations et services de la Ville de Genève
          </label>
        </div>
        <div class="form-check">
          <label class="form-check-label">
            <input class="form-check-input" type="checkbox" v-model="contact.services.consulting">
            Conseils sur le monde associatif
          </label>
        </div>
        <div class="form-check">
          <label class="form-check-label">
            <input class="form-check-input" type="checkbox" v-model="contact.services.funding">
            Aide à la recherche de partenariats et de fonds
          </label>
        </div>
        <div class="form-check">
          <label class="form-check-label">
            <input class="form-check-input" type="checkbox" v-model="contact.services.eventPlanning">
            Organisation d'événements
          </label>
        </div>
        <div class="form-check">
          <label class="form-check-label">
            <input class="form-check-input" type="checkbox" v-model="contact.services.travelPlanning">
            Organisation de voyages
          </label>
        </div>
        <div class="form-check">
          <label class="form-check-label">
            <input class="form-check-input" type="checkbox" v-model="contact.services.partyPlanning">
            Organisation de soirées
          </label>
        </div>
        <div class="form-check">
          <label class="form-check-label">
            <input class="form-check-input" type="checkbox" v-model="contact.services.ongs">
            Contacts avec les ONGs
          </label>
        </div>
        <div class="form-check">
          <label class="form-check-label">
            <input class="form-check-input" type="checkbox" v-model="contact.services.other">
            Autre
          </label>
        </div>
        <div class="form-group" v-if="contact.services.other">
          <label for="contactInputServiceOther">Autre(s) service(s)</label>
          <textarea class="form-control" id="contactInputServiceOther" rows="8" cols="80" v-model="contact.services.otherText"></textarea>
        </div>
      </div>

      <div class="alert alert-danger" role="alert" v-if="formIsSubmitted && !formIsValid">
        Une/plusieurs erreur(s) est/sont présente(s) dans le formulaire; merci de la/les corriger.
      </div>

      <button type="submit" class="btn btn-primary">Envoyer</button>
    </form>

    <div class="alert alert-success" role="alert" v-if="formSubmittedSuccessfully">
      Merci de nous avoir transmis votre demande, un gestionnaire de notre équipe prendra rapidement contact avec vous.
    </div>

    <div class="alert alert-danger" role="alert" v-if="errorAfterSubmission">
      Une erreur s'est produite lors de la soumission du formulaire. Merci de réessayer ou de <a href="mailto:julien.grunhagel@lyoxa.ch" class="alert-link">contacter le support</a>.
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      formIsSubmitted: false,
      servicesAreInvalid: false,
      formIsValid: false,
      formSubmittedSuccessfully: false,
      errorAfterSubmission: false,
      contact: {
        firstName: '',
        name: '',
        email: '',
        phone: '',
        association: '',
        demand: '',
        services: {
          statusLegal: false,
          budgets: false,
          teamManagement: false,
          teamBuilding: false,
          communicationDesign: false,
          autorisations: false,
          consulting: false,
          funding: false,
          eventPlanning: false,
          travelPlanning: false,
          partyPlanning: false,
          ongs: false,
          other: false,
          otherText: ''
        }
      }
    }
  },
  methods: {
    validateForm () {
      const form = document.getElementById('needs-validation')
      if (form.checkValidity() === false) {
        event.preventDefault()
        event.stopPropagation()
      } else {
        this.formIsValid = true
        return true
      }
      form.classList.add('was-validated')
      return false
    },
    onSubmit () {
      this.formIsSubmitted = true
      if (this.validateForm()) {
        let apiURL = 'https://bp60k0083l.execute-api.eu-central-1.amazonaws.com/prod/lyoxaFormSlack'
        this.$http.post(apiURL, JSON.stringify(this.contact))
          .then(response => {
            this.formSubmittedSuccessfully = true
            this.errorAfterSubmission = false
          }, response => {
            this.formSubmittedSuccessfully = false
            this.errorAfterSubmission = true
          })
      }
    }
  }
}
</script>
