<script setup lang="ts">

import {ref} from "vue";

let sorties = ref(null);

fetch("http://10.16.200.2:8000/api/sorties.json")
    .then(res => res.json())
    .then(json => sorties.value = json)

</script>

<template>
  <div v-if="sorties">
    <div v-for="sortie of sorties">
      {{ sortie.nom }}
    </div>
  </div>
</template>

<style scoped></style>