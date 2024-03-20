<script setup lang="ts">

//import ZuButton from './components/ZuButton.vue'

import { ZuButton, ZuInput } from '../dist/zu-vue';

import "../dist/zu.css"

</script>

<template>

    <div class="container p-3">

        <div class="text-center">
            <img class="text-center" src="/logo-zupah.svg" />
        </div>

        <h3 class="mt-3 text-center">library vue</h3>

        <div class="row mt-5">
            <div class="col">
                <ZuInput id="email" type="email" class="mt-30" label="E-mail"></ZuInput>
            </div>
        </div>

        <div class="mt-3">
            <ZuButton label="Enviar" name="enviar" type="button">

            </ZuButton>
        </div>



        <div class="mt-3">
            <!-- Button trigger modal -->
            <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
                Launch demo modal
            </button>


            <!-- Modal -->
            <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel"
                aria-hidden="true">
                <div class="modal-dialog">
                    <div class="modal-content">
                        <div class="modal-header">
                            <h1 class="modal-title fs-5" id="exampleModalLabel">Modal title</h1>
                            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                        </div>
                        <div class="modal-body">
                            ...
                        </div>
                        <div class="modal-footer">
                            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                            <button type="button" class="btn btn-primary">Save changes</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>


        <!-- Example split danger button -->
        <div class="mt-3">


            <div class="btn-group">
                <button type="button" class="btn zu-button">Action</button>
                <button type="button" class="btn zu-button dropdown-toggle dropdown-toggle-split"
                    data-bs-toggle="dropdown" aria-expanded="false">
                    <span class="visually-hidden">Toggle Dropdown</span>
                </button>
                <ul class="dropdown-menu">
                    <li><a class="dropdown-item" href="#">Action</a></li>
                    <li><a class="dropdown-item" href="#">Another action</a></li>
                    <li><a class="dropdown-item" href="#">Something else here</a></li>
                    <li>
                        <hr class="dropdown-divider">
                    </li>
                    <li><a class="dropdown-item" href="#">Separated link</a></li>
                </ul>
            </div>
        </div>

    </div>


</template>

<style scoped></style>
