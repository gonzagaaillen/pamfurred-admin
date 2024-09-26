<script setup lang="ts">
import InputGroup from 'primevue/inputgroup'
import InputGroupAddon from 'primevue/inputgroupaddon'
import InputText from 'primevue/inputtext'
import Button from 'primevue/button'
import FloatLabel from 'primevue/floatlabel'
import { computed, ref } from 'vue'

const username = ref<string>('')
const password = ref<string>('')
const isLoginDisabled = computed(() => !username.value || !password.value)
</script>

<template>
  <div class="login">
    <div class="flex flex-wrap align-items-center justify-content-center">
      <div
        class="my-2 border-round bg-primary font-bold flex align-items-center justify-content-center"
      >
        <img alt="Pamfurred Logo" src="@/assets/PamfurredLogo.png" class="logo" />
      </div>
    </div>

    <div
      class="min-w-min md:min-w-max border-round bg-primary font-bold p-3 flex align-items-center justify-content-center"
    >
      <div class="flex flex-column row-gap-5">
        <InputGroup>
          <InputGroupAddon>
            <i class="pi pi-user"></i>
          </InputGroupAddon>
          <FloatLabel>
            <InputText id="username" v-model="username" />
            <label for="username">Username</label>
          </FloatLabel>
        </InputGroup>

        <InputGroup>
          <InputGroupAddon>
            <i class="pi pi-lock"></i>
          </InputGroupAddon>
          <FloatLabel>
            <InputText type="password" id="password" v-model="password" />
            <label for="password">Password</label>
          </FloatLabel>
        </InputGroup>
      </div>
    </div>
    <div class="flex justify-between items-center">
      <a href="#" class="forgot-password">Forgot password?</a>
    </div>
    <div class="flex flex-wrap align-items-center justify-content-center">
      <Button label="Login" :disabled="isLoginDisabled" />
    </div>
  </div>
</template>
