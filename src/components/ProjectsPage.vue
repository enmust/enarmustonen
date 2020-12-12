<template>
  <div class="projects-page mx-2 mx-md-0">
    <div class="d-flex justify-center mt-16 mb-12" style="font-size: 3rem;">
      <div
        class="animate__animated animate__bounceInUp"
        style="border-bottom: 4px solid #2196F3;"
      >
        Projects
      </div>
    </div>

    <v-row no-gutters>
      <v-col cols="12" class="px-1 my-3">
        Some projects I have made...
      </v-col>
    </v-row>

    <v-row no-gutters>
      <v-col
        cols="12"
        :sm="projects[item].sm"
        :md="projects[item].md"
        v-for="item in projectIds"
        :key="item"
        class="pa-1"
      >
        <v-hover
          v-slot="{ hover }"
          close-delay="1000"
          :style="
            `background: url(&quot;${projects[item].image}&quot;) rgba(0,0,0,0.2); background-blend-mode: overlay; background-size: cover; background-position: center; background-repeat: no-repeat;`
          "
        >
          <v-card
            tile
            height="300"
            @mouseleave="handleMouseLeave(item)"
            @mouseenter="handleMouseEnter(item)"
          >
            <v-overlay color="blue" absolute :value="hover">
              <div class="d-flex flex-column text-center">
                <div
                  class="font-weight-bold animate__animated"
                  :class="{
                    animate__bounceIn: hover,
                    animate__bounceOut: projects[item].isLeaving
                  }"
                  style="font-size: 1.5rem;"
                >
                  {{ projects[item].name }}
                </div>

                <div
                  class="mb-12 animate__animated font-weight-medium"
                  :class="{
                    animate__bounceIn: hover,
                    animate__bounceOut: projects[item].isLeaving
                  }"
                >
                  {{ projects[item].tech }}
                </div>

                <div
                  class="mt-12 animate__animated"
                  :class="{
                    animate__bounceIn: hover,
                    animate__bounceOut: projects[item].isLeaving
                  }"
                >
                  <v-btn
                    v-if="projects[item].link"
                    small
                    outlined
                    tile
                    :href="projects[item].link"
                    target="_blank"
                    ><b>Visit site</b>
                    <v-icon right x-small>fas fa-external-link-alt </v-icon>
                  </v-btn>
                </div>
              </div>
            </v-overlay>
          </v-card>
        </v-hover>
      </v-col>
    </v-row>

    <v-row no-gutters>
      <v-col cols="12" class="px-1 my-3">
        <div style="max-width: 600px;">
          That's not all, there are many more, for example some project have
          included Raspberry Pi-s, Arduino boards etc.
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "ProjectsPage",
  data: () => ({
    overlay: false,
    projects: {
      geocase: {
        name: "GeoCASe 2.0",
        image: require("@/assets/projects/geocase.jpg"),
        tech:
          "Data network of geological collections from from different institutions",
        link: "https://geocase.geocollections.info",
        isLeaving: false,
        sm: 6,
        md: 4
      },
      geocaseApi: {
        name: "GeoCASe API",
        image: require("@/assets/projects/geocase-api.png"),
        tech: "Public API for the GeoCASe 2.0",
        link: "https://geocase-api.geocollections.info",
        isLeaving: false,
        sm: 6,
        md: 4
      },
      turba: {
        name: "TURBA",
        image: require("@/assets/projects/turba.jpg"),
        tech: "Estonian peat studies database",
        link: "https://turba.geoloogia.info",
        isLeaving: false,
        sm: 6,
        md: 4
      },
      sarvDoi: {
        name: "SARV·DOI",
        image: require("@/assets/projects/doi.jpg"),
        tech:
          "Application to showcase articles, documents etc. which have an official DOI number",
        link: "https://doi.geocollections.info",
        isLeaving: false,
        sm: 6,
        md: 7
      },
      sarvEdit: {
        name: "SARV Data Management",
        image: require("@/assets/projects/sarv.jpg"),
        tech: "Geocollections Data Management, basically a CRUD app",
        link: "https://edit.geocollections.info",
        isLeaving: false,
        sm: 6,
        md: 5
      },
      geocollections: {
        name: "Geocollections",
        image: require("@/assets/projects/geocollections.jpg"),
        tech: "Geoscience Collections of Estonia",
        link: "https://geocollections.info",
        isLeaving: false,
        sm: 6,
        md: 5
      },
      geocollectionsApi: {
        name: "Geocollections API",
        image: require("@/assets/projects/geocollectionsApi.jpg"),
        tech: "Public Geocollections API which supports multiple applications",
        link: "https://api.geocollections.info",
        isLeaving: false,
        sm: 6,
        md: 7
      },
      eurocore: {
        name: "EuroCore",
        image: require("@/assets/projects/eurocore.jpg"),
        tech: "Portal which provides data from drill cores",
        link: "https://eurocore.rocks",
        isLeaving: false,
        sm: 6,
        md: 4
      },
      chuckNorrisVue: {
        name: "Chuck Norris Facts (Vue)",
        image: require("@/assets/projects/chuckNorrisVue.jpg"),
        tech: "Made to test Vue",
        link: null,
        isLeaving: false,
        sm: 6,
        md: 4
      },
      readySteadyGo: {
        name: "Ready Steady Go",
        image: require("@/assets/projects/randomStart.png"),
        tech: "Fun app which was intended for arm wrestling",
        link: null,
        isLeaving: false,
        sm: 6,
        md: 4
      },
      chuckNorrisReact: {
        name: "Chuck Norris Facts (React)",
        image: require("@/assets/projects/chuckNorrisReact.jpg"),
        tech: "Made to test React",
        link: null,
        isLeaving: false,
        sm: 12,
        md: 6
      },
      resourcing: {
        name: "RE-SOURCING",
        image: require("@/assets/projects/resourcing.jpg"),
        tech: "A global stakeholder platform for responsible sourcing",
        link: null,
        isLeaving: false,
        sm: 12,
        md: 6
      }
    },
    projectIds: [
      "geocase",
      "geocaseApi",
      "turba",
      "sarvDoi",
      "sarvEdit",
      "geocollections",
      "geocollectionsApi",
      "eurocore",
      "chuckNorrisVue",
      "readySteadyGo",
      "chuckNorrisReact",
      "resourcing"
    ]
  }),
  methods: {
    handleMouseLeave(id) {
      if (!this.projects[id].isLeaving)
        setTimeout(() => (this.projects[id].isLeaving = true), 400);
    },

    handleMouseEnter(id) {
      if (this.projects[id].isLeaving) this.projects[id].isLeaving = false;
    }
  }
};
</script>

<style scoped></style>
