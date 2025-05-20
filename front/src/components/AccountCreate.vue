<template>
  <div class="w-full">
    <h2 class="text-2xl font-bold mb-6 text-center">Créer un compte pour créer des histoires</h2>
    <UForm :schema="schema" :state="state" @submit="onSubmit" class="w-full space-y-4">
      <UFormField label="Email" name="email" class="w-full">
        <UInput v-model="state.email" class="w-full" />
      </UFormField>

      <UFormField label="Mot de passe" name="password" class="w-full">
        <UInput v-model="state.password" type="password" class="w-full" />
      </UFormField>

      <UButton type="submit" icon="i-lucide-rocket" class="mt-4">Créer mon compte</UButton>
    </UForm>
  </div>
</template>

<script setup lang="ts">
import * as z from 'zod'
import { reactive } from 'vue'
import type { FormSubmitEvent } from '@nuxt/ui'

const schema = z.object({
  email: z.string().email('Invalid email'),
  password: z.string().min(8, 'Must be at least 8 characters'),
})

type Schema = z.output<typeof schema>

const state = reactive<Partial<Schema>>({
  email: undefined,
  password: undefined,
})

const toast = useToast()
async function onSubmit(event: FormSubmitEvent<Schema>) {
  event.preventDefault()
  const { email, password } = event.data
  if (!email || !password) {
    toast.add({ title: 'Error', description: 'Email and password are required.', color: 'danger' })
    return
  }
  // Simulate an API call
  await new Promise((resolve) => setTimeout(resolve, 1000))
  // Here you would typically send the data to your backend
  // For example: await api.post('/api/account', { email, password })
  // Simulate a successful response
  // You can replace this with your actual API call
  // const response = await api.post('/api/account', { email, password })
  // if (response.status !== 200) {
  //   toast.add({ title: 'Error', description: 'Failed to create account.', color: 'danger' })
  //   return
  // }
  // Simulate a successful account creation
  // You can replace this with your actual API call
  // const response = await api.post('/api/account', { email, password })
  // if (response.status !== 200) {
  //   toast.add({ title: 'Error', description: 'Failed to create account.', color: 'danger' })
  //   return
  // }

  toast.add({ title: 'Success', description: 'Votre compte a été créé avec succès.', color: 'success' })
  console.log(event.data)
}
</script>
