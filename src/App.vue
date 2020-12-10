<template>
  <v-app>
    <v-main>
      <LandingPage />

      <NameToolbar />

      <v-container>
        <AboutPage />

        <ProjectsPage />

        <ContactPage />
      </v-container>

      <Footer />
    </v-main>
  </v-app>
</template>

<script>
import LandingPage from "@/components/LandingPage";
import NameToolbar from "@/components/NameToolbar";
import AboutPage from "@/components/AboutPage";
import ContactPage from "@/components/ContactPage";
import ProjectsPage from "@/components/ProjectsPage";
import Footer from "@/components/Footer";

export default {
  name: "App",

  components: {
    Footer,
    ProjectsPage,
    ContactPage,
    AboutPage,
    NameToolbar,
    LandingPage
  },

  data: () => ({
    //
  })
};
</script>

<style>
.v-application {
  font-family: "Raleway", sans-serif !important;
  -webkit-font-smoothing: antialiased;
}
</style>
