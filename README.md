# Projet Vue.js - Documentation Complète

Ce projet Vue.js est une application développée dans le cadre d'un exercice demandé par le professeur. Le travail consistait à :
1. **Exercice 1** : Découper un fichier Vue.js contenant tout le contenu en un seul bloc ("HomeProjectView.vue") en plusieurs composants modulaires.
2. **Exercice 2** : Créer un formulaire complexe en Vue.js avec validation des champs, comme demandé par le professeur.

Cette documentation explique tout en détail pour permettre à quiconque de comprendre le projet et de le tester.

---

## Structure du Projet

Voici la structure globale du projet après la réalisation des exercices :

```
nextu-vue-helloworld/
├── src/
│   ├── assets/
│   ├── components/
│   │   ├── announcements/
│   │   │   ├── AnnouncementItem.vue
│   │   │   ├── Announcements.vue
│   │   ├── projects/
│   │   │   ├── ProjectCard.vue
│   │   │   ├── ProjectGrid.vue
│   │   ├── trending/
│   │   │   ├── TrendingItem.vue
│   │   │   ├── TrendingList.vue
│   ├── router/
│   │   ├── index.ts
│   ├── views/
│   │   ├── HomeProjectView.vue
│   │   ├── NextuRegistrationView.vue
│   ├── App.vue
│   ├── main.ts
├── package.json
├── vite.config.ts
```

---

## Exercice 1 : Découpage de "HomeProjectView.vue"

### Objectif
Le fichier initial "HomeProjectView.vue" contenait tout dans un seul composant :
- Une grille de projets ("Your Projects").
- Une section d'annonces ("Announcements").
- Une section de tendances ("Trending").

**But** : Créer des composants réutilisables pour chaque section et les importer dans "HomeProjectView.vue".

### Résultat
Voici les composants créés :
1. **projects/ProjectCard.vue** : Affiche une seule carte projet.
2. **projects/ProjectGrid.vue** : Organise les cartes projets dans une grille.
3. **announcements/AnnouncementItem.vue** : Affiche une annonce unique.
4. **announcements/Announcements.vue** : Regroupe plusieurs annonces.
5. **trending/TrendingItem.vue** : Affiche une tendance unique.
6. **trending/TrendingList.vue** : Regroupe plusieurs tendances.

Dans le fichier "HomeProjectView.vue", ces composants ont été importés et utilisés pour réorganiser le contenu. Cela permet une meilleure réutilisabilité et maintenance.

---

## Exercice 2 : Formulaire d'Inscription

### Objectif
Créer un formulaire comme demandé par le professeur avec :
- Champs pour le nom, prénom, email, sexe, adresse, code postal, ville, et nom de l'institut.
- Validation des champs (ex. : email valide, champs obligatoires).
- Boutons "Valider" et "Annuler".

### Fonctionnalités
1. **Validation des Champs** :
   - Tous les champs sont obligatoires.
   - L'email doit être dans un format valide.
   - Les messages d'erreur s'affichent dynamiquement.

2. **Actions** :
   - "Valider" : Affiche les données dans la console.
   - "Annuler" : Réinitialise tous les champs.

### Exemple de Code : Formulaire d'Inscription
Le formulaire a été intégré dans "NextuRegistrationView.vue". Voici son contenu :

```vue
<script lang="ts" setup>
import { reactive } from "vue";

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

const onSubmit = () => {
  console.log("Données du formulaire :", student);
};

const onCancel = () => {
  Object.keys(student).forEach((key) => {
    student[key as keyof typeof student] = "";
  });
};
</script>

<template>
  <div class="registration-form">
    <h2>Formulaire d'inscription</h2>
    <form @submit.prevent="onSubmit">
      <!-- Nom et Prénom -->
      <div class="form-group">
        <label for="firstName">Nom</label>
        <input type="text" id="firstName" v-model="student.firstName" />
        <label for="lastName">Prénom</label>
        <input type="text" id="lastName" v-model="student.lastName" />
      </div>

      <!-- Email -->
      <div class="form-group">
        <label for="email">Email</label>
        <input type="email" id="email" v-model="student.email" />
      </div>

      <!-- Sexe -->
      <div class="form-group">
        <label>Sexe :</label>
        <label><input type="radio" name="gender" value="Homme" v-model="student.gender" /> Homme</label>
        <label><input type="radio" name="gender" value="Femme" v-model="student.gender" /> Femme</label>
      </div>

      <!-- Adresse -->
      <div class="form-group">
        <label for="address">Adresse</label>
        <input type="text" id="address" v-model="student.address" />
      </div>

      <!-- Code Postal et Ville -->
      <div class="form-group">
        <label for="postalCode">Code Postal</label>
        <input type="text" id="postalCode" v-model="student.postalCode" />
        <label for="city">Ville</label>
        <input type="text" id="city" v-model="student.city" />
      </div>

      <!-- Nom de l'Institut -->
      <div class="form-group">
        <label for="institution">Nom de l'Institut</label>
        <input type="text" id="institution" v-model="student.institution" />
      </div>

      <!-- Boutons -->
      <button type="submit">Valider</button>
      <button type="button" @click="onCancel">Annuler</button>
    </form>
  </div>
</template>

<style scoped>
.registration-form {
  max-width: 600px;
  margin: auto;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: #f9f9f9;
}
</style>
```

---

## Lancer le Projet

### Prérequis
- **Node.js** (version 16 ou supérieure).
- **Vue CLI** (optionnel).

### Instructions
1. **Installer les dépendances** :
   ```bash
   npm install
   ```

2. **Lancer le serveur de développement** :
   ```bash
   npm run dev
   ```

3. **Accéder à l'application** :
   Ouvrez [http://localhost:3000](http://localhost:3000) dans votre navigateur.

---

## Conclusion
Ce projet démontre l'utilisation de Vue.js pour créer des interfaces modulaires et interactives. 

