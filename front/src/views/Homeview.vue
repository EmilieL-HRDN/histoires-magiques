<template>
  <div class="min-h-screen flex flex-col items-center">
    <!-- Header -->
    <header class="flex justify-between items-center p-6 w-full">
      <h1 class="text-2xl font-bold">Histoires Magiques</h1>
      <button
        class="bg-[#E3AF6A] text-white px-4 py-2 rounded-2xl shadow hover:bg-[#d99b55] transition"
      >
        Créer une histoire
      </button>
    </header>

    <!-- Hero -->
    <section
      class="container flex-1 max-w-[1200px] mx-auto flex flex-col gap-10 items-center text-center py-16"
    >
      <h2 class="text-4xl md:text-5xl font-bold mb-4">
        Inventez des histoires enchantées en quelques clics
      </h2>
      <p class="text-lg max-w-xl mb-8 text-gray-600">
        Choisissez un héros, un lieu magique, un thème… et laissez l’intelligence artificielle
        inventer un conte sur-mesure pour votre enfant.
      </p>
      <button
        class="bg-[#545D98] text-white px-6 py-3 rounded-full font-semibold shadow hover:bg-[#454c7f] transition"
        @click="showModal = true"
      >
        Commencer l’aventure
      </button>
    </section>

    <!-- Étapes -->
    <section class="grid md:grid-cols-3 gap-8 px-6 pb-20">
      <div class="bg-white rounded-2xl p-6 shadow-md text-center">
        <h3 class="text-xl font-semibold mb-2">1. Choisissez</h3>
        <p>Le héros, le lieu, l’ambiance…</p>
      </div>
      <div class="bg-white rounded-2xl p-6 shadow-md text-center">
        <h3 class="text-xl font-semibold mb-2">2. Laissez faire l’IA</h3>
        <p>LangChain et OpenAI créent une histoire unique</p>
      </div>
      <div class="bg-white rounded-2xl p-6 shadow-md text-center">
        <h3 class="text-xl font-semibold mb-2">3. Écoutez ou lisez</h3>
        <p>Partagez un moment magique avec votre enfant</p>
      </div>
    </section>

    <!-- Modale de création de compte -->
    <div
      v-if="showModal"
      class="fixed inset-0 bg-black bg-opacity-40 flex items-center justify-center z-50"
    >
      <div class="bg-white rounded-2xl p-8 shadow-lg w-full max-w-md relative">
        <button
          class="absolute top-3 right-3 text-gray-400 hover:text-gray-700 text-2xl"
          @click="showModal = false"
          aria-label="Fermer"
        >
          &times;
        </button>
        <h2 class="text-2xl font-bold mb-4">Créer un compte</h2>
        <form @submit.prevent="handleSignup">
          <input
            v-model="email"
            type="email"
            placeholder="Adresse e-mail"
            class="w-full mb-3 px-4 py-2 border rounded"
            required
          />
          <input
            v-model="password"
            type="password"
            placeholder="Mot de passe"
            class="w-full mb-4 px-4 py-2 border rounded"
            required
          />
          <button
            type="submit"
            class="bg-[#545D98] text-white px-6 py-2 rounded-full font-semibold shadow hover:bg-[#454c7f] transition w-full"
          >
            S’inscrire
          </button>
        </form>
      </div>
    </div>

    <!-- Footer -->
    <footer class="text-center text-sm text-gray-500 pb-6">
      © 2025 Histoires Magiques. Créé avec amour et IA 🧠✨
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const showModal = ref(false)
const email = ref('')
const password = ref('')

function handleSignup() {
  // Ici tu ajoutes la logique d'inscription (API, etc.)
  alert(`Compte créé pour ${email.value} !`)
  showModal.value = false
}
</script>

<style scoped>
/* Ajoute des animations douces si tu veux */
</style>
