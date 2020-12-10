<template>
  <v-footer padless>
    <v-card class="flex" flat tile>
      <v-card-text class="text-center">
        {{ new Date().getFullYear() }} - <b>Enar Mustonen</b>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  name: "Footer"
};
</script>

<style scoped></style>
