<script setup lang="ts">

//import ZuButton from './components/ZuButton.vue'

import { ZuButton, ZuInput } from '../dist/zu-vue';
import "../dist/style.css"

</script>

<template>
    <h1>zupah library vue</h1>

    <img src="logo-zupah.svg" />



    <ZuInput id="email" type="email" class="mt-30" label="E-mail">

    </ZuInput>

    <ZuButton label="Enviar" name="enviar" type="button">

    </ZuButton>
</template>

<style scoped></style>
