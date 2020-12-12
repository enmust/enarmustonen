<template>
  <div class="about-page mx-2 mx-md-0">
    <div class="d-flex justify-center mt-16 mb-12" style="font-size: 3rem;">
      <div
        class="animate__animated animate__bounceInUp"
        style="border-bottom: 4px solid #2196F3;"
      >
        About
      </div>
    </div>

    <div class="d-flex flex-column flex-md-row justify-space-between">
      <div class="d-flex flex-column">
        <div class="align-self-center  animate__animated animate__zoomIn">
          <v-hover v-slot="{ hover }" close-delay="800">
            <v-img
              class="rounded-circle profile-picture"
              :class="{ 'animate__animated animate__jello': hover }"
              height="200"
              width="200"
              aspect-ratio="1"
              :src="require('@/assets/profile_picture.jpg')"
              alt="Enar"
            />
          </v-hover>
        </div>

        <div
          class="mt-4 align-self-center align-self-md-start text-center text-md-start animate__animated animate__zoomIn"
          style="max-width: 600px;"
        >
          I am Enar a full-stack web developer from Estonia. Born in
          <a
            class="font-weight-bold text-decoration-none"
            href="https://www.google.com/search?q=P%C3%A4rnu,%20Estonia"
            target="NewWindow"
            >Pärnu</a
          >
          living in Tallinn.
        </div>

        <div class="align-self-center mt-2 animate__animated animate__zoomIn">
          <v-tooltip bottom v-for="btn in socials" :key="btn.name">
            <template v-slot:activator="{ on, attrs }">
              <v-btn
                v-bind="attrs"
                v-on="on"
                :href="btn.link"
                :target="btn.target"
                icon
                large
                color="blue"
                class="mx-1"
                :aria-label="btn.name"
              >
                <v-icon>{{ btn.icon }}</v-icon>
              </v-btn>
            </template>
            <span>{{ btn.name }}</span>
          </v-tooltip>
        </div>
      </div>

      <div class="d-flex flex-column flex-sm-row flex-md-column my-14 my-md-0">
        <div class="d-flex flex-column flex-sm-row justify-space-around my-2">
          <v-hover v-slot="{ hover }" close-delay="800">
            <div class="mx-2 my-2 my-sm-0 text-center animate__animated animate__zoomIn">
              <div class="d-flex justify-center">
                <v-card
                  :class="{ 'animate__animated animate__wobble': hover }"
                  color="blue"
                  dark
                  shaped
                  class="mb-2 pa-3"
                >
                  <v-icon x-large>fas fa-desktop</v-icon>
                </v-card>
              </div>
              <div class="font-weight-bold" style="font-size: 1.5rem;">
                Responsive
              </div>
              <div class="mx-auto" style="max-width: 225px;">
                Pages will work on any screen size and on any device
              </div>
            </div>
          </v-hover>

          <v-hover v-slot="{ hover }" close-delay="800">
            <div class="mx-2 my-2 my-sm-0 text-center animate__animated animate__zoomIn">
              <div class="d-flex justify-center">
                <v-card
                  :class="{ 'animate__animated animate__wobble': hover }"
                  color="blue"
                  dark
                  shaped
                  class="mb-2 pa-3"
                >
                  <v-icon x-large>fas fa-chart-line</v-icon>
                </v-card>
              </div>
              <div class="font-weight-bold" style="font-size: 1.5rem;">
                Dynamic
              </div>
              <div class="mx-auto" style="max-width: 225px;">Web pages will come alive</div>
            </div>
          </v-hover>
        </div>

        <div class="d-flex flex-column flex-sm-row justify-space-around my-2">
          <v-hover v-slot="{ hover }" close-delay="800">
            <div class="mx-2 my-2 my-sm-0 text-center animate__animated animate__zoomIn">
              <div class="d-flex justify-center">
                <v-card
                  :class="{ 'animate__animated animate__wobble': hover }"
                  color="blue"
                  dark
                  shaped
                  class="mb-2 pa-3"
                >
                  <v-icon x-large>fas fa-pencil-ruler</v-icon>
                </v-card>
              </div>
              <div class="font-weight-bold" style="font-size: 1.5rem;">
                Tailored
              </div>
              <div class="mx-auto" style="max-width: 225px;">
                Custom solutions from beginning to end
              </div>
            </div>
          </v-hover>

          <v-hover v-slot="{ hover }" close-delay="800">
            <div class="mx-2 my-2 my-sm-0 text-center animate__animated animate__zoomIn">
              <div class="d-flex justify-center">
                <v-card
                  :class="{ 'animate__animated animate__wobble': hover }"
                  color="blue"
                  dark
                  shaped
                  class="mb-2 pa-3"
                >
                  <v-icon large>fas fa-tachometer-alt</v-icon>
                </v-card>
              </div>
              <div class="font-weight-bold" style="font-size: 1.5rem;">
                Fast
              </div>
              <div class="mx-auto" style="max-width: 225px;">
                Minimal load times without any lag
              </div>
            </div>
          </v-hover>
        </div>
      </div>
    </div>

    <div class="mb-16 mt-0 mt-md-14 text-center">
      <span v-for="(entity, index) in tags" :key="index">
        <v-hover v-slot="{ hover }" close-delay="800">
          <v-chip
            dark
            class="ma-1 animate__animated font-weight-medium"
            color="blue"
            :class="{ animate__rollOut: hover, animate__rollIn: !hover }"
            >{{ entity }}</v-chip
          >
        </v-hover>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: "AboutPage",
  data: () => ({
    socials: [
      {
        name: "GitHub",
        link: "https://github.com/enmust",
        target: "SocialWindow",
        icon: "fab fa-github"
      },
      {
        name: "Instagram",
        link: "https://www.instagram.com/enarmustonen/",
        target: "SocialWindow",
        icon: "fab fa-instagram"
      },
      {
        name: "Facebook",
        link: "https://www.facebook.com/enar.mustonen",
        target: "SocialWindow",
        icon: "fab fa-facebook"
      },
      {
        name: "Mail",
        link: "mailto:enar.mustonen@gmail.com",
        target: "",
        icon: "far fa-envelope"
      },
      {
        name: "Phone",
        link: "tel:+37253471868",
        target: "",
        icon: "fas fa-phone-alt"
      }
    ],
    tags: [
      "JavasScript",
      "HTML",
      "CSS",
      "Vue",
      "Vuex",
      "Docker",
      "Linux",
      "Django",
      "Django REST framework",
      "REST API",
      "CircleCI",
      "Python",
      "Node",
      "Express",
      "Git",
      "PostgreSQL",
      "MySQL",
      "React",
      "Apache Solr",
      "Angular",
      "TypeScript",
      "Webpack",
      "Java",
      "Apache",
      "NGINX",
      "Continuous Integration",
      "Leaflet",
      "Postman",
      "CRUD",
      "etc."
    ]
  })
};
</script>

<style scoped>
.profile-picture {
  border: 4px solid #2196f3;
}
</style>
