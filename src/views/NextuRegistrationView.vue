<script lang="ts" setup>
import { reactive } from "vue";

// Structure des données pour le formulaire
const student = reactive({
  firstName: "",
  lastName: "",
  email: "",
  gender: "",
  address: "",
  postalCode: "",
  city: "",
  institution: "",
});

// Fonction pour soumettre le formulaire
const onSubmit = () => {
  console.log("Données du formulaire :", student);
};

// Fonction pour réinitialiser le formulaire
const onCancel = () => {
  Object.keys(student).forEach((key) => {
    student[key as keyof typeof student] = "";
  });
};
</script>

<template>
  <div class="registration-form">
    <h2>Formulaire d'inscription</h2>

    <!-- Affichage des erreurs -->
    <div v-if="!student.email.includes('@')" class="error">
      - Champ email incorrect
    </div>

    <form @submit.prevent="onSubmit">
      <!-- Nom et Prénom -->
      <div class="form-group">
        <label for="firstName">Nom</label>
        <input
          type="text"
          id="firstName"
          v-model="student.firstName"
          placeholder="Entrez votre nom"
        />
        <label for="lastName">Prénom</label>
        <input
          type="text"
          id="lastName"
          v-model="student.lastName"
          placeholder="Entrez votre prénom"
        />
      </div>

      <!-- Email -->
      <div class="form-group">
        <label for="email">Email</label>
        <input
          type="email"
          id="email"
          v-model="student.email"
          placeholder="Entrez votre email"
        />
      </div>

      <!-- Sexe -->
      <div class="form-group">
        <label>Sexe :</label>
        <div class="radio-group">
          <label>
            <input
              type="radio"
              name="gender"
              value="Homme"
              v-model="student.gender"
            />
            Homme
          </label>
          <label>
            <input
              type="radio"
              name="gender"
              value="Femme"
              v-model="student.gender"
            />
            Femme
          </label>
        </div>
      </div>

      <!-- Adresse, Code Postal et Ville -->
      <div class="form-group">
        <label for="address">Adresse</label>
        <input
          type="text"
          id="address"
          v-model="student.address"
          placeholder="Entrez votre adresse"
        />
      </div>

      <div class="form-group inline">
        <label for="postalCode">Code Postal</label>
        <input
          type="text"
          id="postalCode"
          v-model="student.postalCode"
          placeholder="Code postal"
        />
        <label for="city">Ville</label>
        <input
          type="text"
          id="city"
          v-model="student.city"
          placeholder="Ville"
        />
      </div>

      <!-- Nom de l'institut -->
      <div class="form-group">
        <label for="institution">Nom de l'institut</label>
        <input
          type="text"
          id="institution"
          v-model="student.institution"
          placeholder="Entrez le nom de l'institut"
        />
      </div>

      <!-- Boutons -->
      <div class="button-group">
        <button type="submit">Valider</button>
        <button type="button" @click="onCancel">Annuler</button>
      </div>
    </form>
  </div>
</template>

<style scoped>
.registration-form {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: #f9f9f9;
}

h2 {
  text-align: center;
  margin-bottom: 24px;
}

.form-group {
  margin-bottom: 16px;
}

.form-group.inline {
  display: flex;
  gap: 16px;
}

label {
  display: block;
  margin-bottom: 8px;
  font-weight: bold;
}

input[type="text"],
input[type="email"],
button {
  width: 100%;
  padding: 10px;
  margin-bottom: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

input[type="radio"] {
  margin-right: 8px;
}

.radio-group {
  display: flex;
  gap: 16px;
}

button {
  padding: 12px 20px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

.button-group {
  display: flex;
  justify-content: space-between;
}

.error {
  color: red;
  margin-bottom: 16px;
}
</style>
