<template>
  <v-toolbar class="name-toolbar" dense>
    <div class="d-flex justify-space-between" style="width: 100%">
      <div
        class="font-weight-bold align-self-center animate__animated animate__slideInLeft"
        style="letter-spacing: 1.75px;"
      >
        Enar Mustonen
      </div>

      <div class="d-flex flex-row flex-nowrap">
        <div
          @click="$vuetify.goTo(`${btn.class}`)"
          v-for="btn in buttons"
          :key="btn.text"
          class="pa-2 toolbar-button hidden-xs-only"
          :class="btn.animateClass"
        >
          {{ btn.text }}
        </div>
      </div>
    </div>
  </v-toolbar>
</template>

<script>
export default {
  name: "NameToolbar",

  data: () => ({
    buttons: [
      {
        text: "About",
        class: ".about-page",
        animateClass: "animate__animated animate__slideInRight"
      },
      {
        text: "Projects",
        class: ".projects-page",
        animateClass: "animate__animated animate__slideInRight animate__slow"
      },
      {
        text: "Contact",
        class: ".contact-page",
        animateClass: "animate__animated animate__slideInRight animate__slower"
      }
    ]
  })
};
</script>

<style scoped>
.name-toolbar {
  border-bottom: 4px solid rgb(33, 150, 243);
  box-shadow: 0 4px 4px rgba(0, 0, 0, 0.2) !important;
}

.toolbar-button {
  /*color: unset;*/
  transition: all 200ms ease-out;
}

.toolbar-button:hover {
  cursor: pointer;
  color: #2196f3;
  transition: color 200ms ease-in;
}
</style>
