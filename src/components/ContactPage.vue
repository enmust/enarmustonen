<template>
  <div class="contact-page">
    <div class="d-flex justify-center mt-16 mb-12" style="font-size: 3rem;">
      <div
        class="animate__animated animate__bounceInUp"
        style="border-bottom: 4px solid #2196F3;"
      >
        Contact
      </div>
    </div>

    <div class="d-flex ma-2 justify-center">
      <div class="px-1">
        If you have any questions or need help with some project etc. feel free
        to contact me.
      </div>
    </div>

    <div
      class="d-flex flex-column flex-sm-row justify-center text-center mb-16"
    >
      <div class="px-2">
        <v-btn
          icon
          href="mailto:enar.mustonen@gmail.com"
          color="blue"
          aria-label="e-mail me"
        >
          <v-icon>far fa-envelope</v-icon>
        </v-btn>
      </div>

      <a
        class="align-self-center email text-decoration-none pa-1"
        href="mailto:enar.mustonen@gmail.com"
        >enar.mustonen@gmail.com</a
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "ContactPage"
};
</script>

<style scoped>
.email {
  color: unset;
  transition: all 200ms ease-out;
}

.email:hover {
  cursor: pointer;
  color: #2196f3;
  transition: color 200ms ease-in;
}
</style>
