<template>
  <div class="d-flex justify-center" style="height: 100vh;">
    <div class="align-self-center text-center">
      <div
        :class="{
          'large-font': $vuetify.breakpoint.smAndUp,
          'small-font': $vuetify.breakpoint.xsOnly
        }"
        class="animate__animated animate__zoomInDown animate__faster"
      >
        <span>Hey, I'm </span>
        <span class="font-weight-bold blue--text">Enar Mustonen</span>
        <span>.</span>
      </div>

      <div
        :class="{
          'large-font': $vuetify.breakpoint.smAndUp,
          'small-font': $vuetify.breakpoint.xsOnly
        }"
        class="animate__animated animate__zoomInDown animate__fast"
      >
        I am a full-stack web developer.
      </div>

      <div class="mt-3 animate__animated animate__zoomInDown">
        <v-btn
          :large="$vuetify.breakpoint.smAndUp"
          :small="$vuetify.breakpoint.xsOnly"
          outlined
          tile
          @click="$vuetify.goTo('.projects-page')"
        >
          View my work
          <v-icon
            right
            :small="$vuetify.breakpoint.smAndUp"
            :x-small="$vuetify.breakpoint.xsOnly"
            >fas fa-angle-double-right</v-icon
          >
        </v-btn>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "LandingPage"
};
</script>

<style scoped>
.large-font {
  font-size: 2rem;
  transition: font-size 200ms ease-in;
}

.small-font {
  font-size: 1.25rem;
  transition: font-size 200ms ease-in;
}
</style>
