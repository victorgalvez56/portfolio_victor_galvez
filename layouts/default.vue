<template>
  <v-app id="inspire">
    <div class="image">
      <v-container>
        <v-row no-gutters>
          <v-col
            cols="12"
          >
            <v-col
              sm="4"
            >
              <v-hover>
                <template v-slot:default="{ hover }">
                  <v-card
                    :elevation="hover ? 24 : 6"
                    class="mx-auto pa-6"
                  >
                    <template slot="progress">
                      <v-progress-linear color="deep-purple" height="10" indeterminate />
                    </template>

                    <v-img height="100%" src="profile.jpg" />

                    <v-card-title class="primary--text">
                      Víctor Gálvez
                    </v-card-title>

                    <v-card-subtitle>
                      Developer Software Fullstack
                    </v-card-subtitle>

                    <v-card-text>
                      <div class="my-4 subtitle-1">
                        $ • Italian, Cafe
                      </div>

                      <div>
                        Small plates, salads & sandwiches - an intimate setting with 12 indoor
                        seats plus patio seating.
                      </div>
                    </v-card-text>

                    <v-divider class="mx-4" />
                  </v-card>
                </template>
              </v-hover>
            </v-col>
            <v-col
              sm="8"
            >
              <v-hover>
                <template
                  v-slot:default="{ hover }"
                >
                  <v-card

                    :elevation="hover ? 24 : 6"
                    class="mx-auto pa-6"
                  >
                    <v-tabs
                      v-model="tab"
                      show-arrows
                      right
                    >
                      <v-tab> About me </v-tab>
                      <v-tab> Activities </v-tab>
                      <v-tab> Portfolio </v-tab>
                      <v-tab> Skills </v-tab>
                      <v-menu
                        v-if="more.length"
                        bottom
                        left
                      >
                        <template v-slot:activator="{ on, attrs }">
                          <v-btn
                            text
                            class="align-self-center mr-4"
                            v-bind="attrs"
                            v-on="on"
                          >
                            options
                            <v-icon right>
                              mdi-menu-down
                            </v-icon>
                          </v-btn>
                        </template>
                        <v-list>
                          <v-list-item-group>
                            <v-list-item>
                              <v-switch
                                v-model="$vuetify.theme.dark"
                                inset
                              />
                              <v-list-item-content>
                                <v-list-item-title>Theme Dark </v-list-item-title>
                              </v-list-item-content>
                            </v-list-item>
                            <v-list-item>
                              <v-list-item-icon>
                                <v-icon>mdi-translate</v-icon>
                              </v-list-item-icon>
                              <v-list-item-content>
                                <v-list-item-title>Idioma </v-list-item-title>
                              </v-list-item-content>
                            </v-list-item>
                          </v-list-item-group>
                        </v-list>
                      </v-menu>
                    </v-tabs>
                    <v-tabs-items v-model="tab">
                      <v-container
                        class="spacing-playground"
                        fluid
                      >
                        <v-tab-item>
                          <v-card flat>
                            <v-card-title class="primary--text">
                              About me
                            </v-card-title>
                            <v-card-text>
                              <div class="text-justify">
                                Hi, I’m Victor. Nice to meet you.
                                Since beginning my journey as a freelance designer nearly 10 years ago,
                                I've done remote work for agencies, consulted for startups, and collaborated with talented people to create digital products for both business and consumer use.
                                I'm quietly confident, naturally curious, and perpetually working on improving my chops one design problem at a time.
                              </div>
                            </v-card-text>
                          </v-card>
                          <v-card flat>
                            <v-card-title class="primary--text">
                              Services
                            </v-card-title>
                            <v-card-text>
                              <v-col
                                cols="12"
                                sm="4"
                              >
                                <v-card
                                  class="mx-auto"
                                >
                                  <div class="hexagon">
                                    <i class="mdi mdi-lightbulb-outline" />
                                  </div>
                                  <v-card-title style="font-size: 15px;">
                                    Web Development
                                  </v-card-title>
                                  <v-card-subtitle>
                                    1,000 miles of wonder
                                  </v-card-subtitle>
                                </v-card>
                              </v-col>
                            </v-card-text>
                          </v-card>
                        </v-tab-item>
                        <v-tab-item>
                          <v-timeline
                            align-top
                            :dense="$vuetify.breakpoint.smAndDown"
                          >
                            <v-timeline-item
                              v-for="(activity, i) in activities"
                              :key="i"
                              :color="activity.color"
                              :icon="activity.icon"
                              fill-dot
                            >
                              <v-card
                                :color="activity.color"
                                dark
                              >
                                <v-card-title class="title">
                                  Lorem Ipsum Dolor
                                </v-card-title>
                                <v-card-text class="white text--primary">
                                  <p>Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.</p>
                                  <v-btn
                                    :color="activity.color"
                                    class="mx-0"
                                    outlined
                                  >
                                    Button
                                  </v-btn>
                                </v-card-text>
                              </v-card>
                            </v-timeline-item>
                          </v-timeline>
                        </v-tab-item>
                        <v-tab-item>
                          <v-card flat>
                            <v-card-title class="primary--text">
                              Frontend
                            </v-card-title>
                            <v-card-text>
                              <div>
                                <v-progress-linear
                                  class="rounded-lg font-italic font-weight-black"
                                  color="red"
                                  height="15"
                                  value="99"
                                  striped
                                >
                                  <strong class="white--text">HTML5 99%</strong>
                                </v-progress-linear>
                                <br>
                                <v-progress-linear
                                  class="rounded-lg font-italic font-weight-black"
                                  color="indigo"
                                  height="15"
                                  value="85"
                                  striped
                                >
                                  <strong class="white--text">CSS3 && SCSS && CSS IN JS 85%</strong>
                                </v-progress-linear>
                                <br>
                                <v-progress-linear
                                  class="rounded-lg font-italic font-weight-black"
                                  height="15"
                                  value="90"
                                  striped
                                  color="purple"
                                >
                                  <strong class="white--text">JAVASCRIPT 90%</strong>
                                </v-progress-linear>
                                <br>
                                <v-progress-linear
                                  class="rounded-lg font-italic font-weight-black"
                                  value="80"
                                  height="15"
                                  striped
                                  color="deep-purple"
                                >
                                  <strong class="white--text">JQUERY 80%</strong>
                                </v-progress-linear>
                                <br>
                                <v-progress-linear
                                  class="rounded-lg font-italic font-weight-black"
                                  value="75"
                                  height="15"
                                  striped
                                  color="indigo darken-1"
                                >
                                  <strong class="white--text">BOOTSTRAP 75%</strong>
                                </v-progress-linear>
                                <br>
                                <v-progress-linear
                                  class="rounded-lg font-italic font-weight-black"
                                  value="60"
                                  height="15"
                                  striped
                                  color="cyan darken-2"
                                >
                                  <strong class="white--text">VUE - VUEX - VUETIFY  60%</strong>
                                </v-progress-linear>
                                <br>
                                <v-progress-linear
                                  class="rounded-lg font-italic font-weight-black"
                                  value="50"
                                  height="15"
                                  striped
                                  color="green darken-4"
                                >
                                  <strong class="white--text">REACT - REACT NATIVE 50%</strong>
                                </v-progress-linear>
                              </div>
                            </v-card-text>
                            <v-card-title class="primary--text">
                              Backend
                            </v-card-title>
                            <v-card-text>
                              <div>
                                <v-progress-linear
                                  color="light-blue"
                                  height="20"
                                  value="90"
                                  striped
                                >
                                  <strong>HTML5 90%</strong>
                                </v-progress-linear>
                                <br>
                                <v-progress-linear
                                  color="light-green darken-4"
                                  height="20"
                                  value="75"
                                  striped
                                >
                                  <strong>CSS3 && SCSS && CSS IN JS 75%</strong>
                                </v-progress-linear>
                                <br>
                                <v-progress-linear
                                  height="20"
                                  value="75"
                                  striped
                                  color="lime"
                                />
                                <br>
                                <v-progress-linear
                                  value="60"
                                  height="20"
                                  striped
                                  color="deep-orange"
                                />
                              </div>
                            </v-card-text>
                            <v-card-title class="primary--text">
                              Frontend
                            </v-card-title>
                            <v-card-text>
                              <div>
                                <v-progress-linear
                                  color="light-blue"
                                  height="20"
                                  value="90"
                                  striped
                                >
                                  <strong>HTML5 90%</strong>
                                </v-progress-linear>
                                <br>
                                <v-progress-linear
                                  color="light-green darken-4"
                                  height="20"
                                  value="75"
                                  striped
                                >
                                  <strong>CSS3 && SCSS && CSS IN JS 75%</strong>
                                </v-progress-linear>
                                <br>
                                <v-progress-linear
                                  height="20"
                                  value="75"
                                  striped
                                  color="lime"
                                />
                                <br>
                                <v-progress-linear
                                  value="60"
                                  height="20"
                                  striped
                                  color="deep-orange"
                                />
                              </div>
                            </v-card-text>
                          </v-card>
                        </v-tab-item>
                      </v-container>
                    </v-tabs-items>
                  </v-card>
                </template>
              </v-hover>
            </v-col>
          </v-col>
        </v-row>
      </v-container>
      <!-- <v-row>
          <v-col cols="3">
            <v-card>
              <template slot="progress">
                <v-progress-linear color="deep-purple" height="10" indeterminate />
              </template>

              <v-img height="250" src="profile.jpg" />

              <v-card-title>Víctor Gálvez</v-card-title>

              <v-card-text>
                <v-row>
                  <div class="grey--text ml-4">
                    Developer Software Fullstack
                  </div>
                </v-row>
                <div class="my-4 subtitle-1">
                  $ • Italian, Cafe
                </div>

                <div>
                  Small plates, salads & sandwiches - an intimate setting with 12 indoor
                  seats plus patio seating.
                </div>
              </v-card-text>

              <v-divider class="mx-4" />
            </v-card>
          </v-col>
          <v-col cols="9">
            <v-card>
              <v-tabs v-model="tab" background-color="primary" dark>
                <v-tab> About me </v-tab>
                <v-tab> Portfolio </v-tab>
                <v-tab> Skills </v-tab>
              </v-tabs>
              <v-tabs-items v-model="tab">
                <v-tab-item>
                  <v-card flat>
                    <v-card-text>asdas</v-card-text>
                  </v-card>
                </v-tab-item>
                <v-tab-item>
                  <v-card flat>
                    <v-card-text>asdasdasdasdasd</v-card-text>
                  </v-card>
                </v-tab-item>
                <v-tab-item>
                  <v-card />
                </v-tab-item>
              </v-tabs-items>
            </v-card>
          </v-col>
        </v-row> -->
    </div>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    tab: null,
    more: [
      'News', 'Maps', 'Books', 'Flights', 'Apps'
    ],
    activities: [
      {
        title: 'Hackathon Oracle Apex 2020',
        subtitle: 'Ellos compitieron con el proyecto “DidacTICloud - Sistema Educativo Peruano”, que los hizo acreedores de 500 dólares. Este proyecto consistió en el desarrollo de una plataforma educativa con un módulo de asistencia para facilitar la comunicación entre alumnos y profesores.',
        color: 'red lighten-2',
        page: 'https://larepublica.pe/nota-de-prensa/2020/12/05/jovenes-arequipenos-obtuvieron-segundo-lugar-en-concurso-tecnologico-lrsd/',
        src: '/hackathon-apex.png',
        icon: 'mdi-vuejs'
      },
      {
        title: 'Hackathon ',
        subtitle: 'Ellos compitieron con el proyecto “DidacTICloud - Sistema Educativo Peruano”, que los hizo acreedores de 500 dólares. Este proyecto consistió en el desarrollo de una plataforma educativa con un módulo de asistencia para facilitar la comunicación entre alumnos y profesores.',
        color: 'purple darken-1',
        page: 'https://larepublica.pe/nota-de-prensa/2020/12/05/jovenes-arequipenos-obtuvieron-segundo-lugar-en-concurso-tecnologico-lrsd/',
        src: '/hackathon-apex.png',
        icon: 'mdi-vuejs'
      },
      {
        title: 'Hackathon ',
        subtitle: 'Ellos compitieron con el proyecto “DidacTICloud - Sistema Educativo Peruano”, que los hizo acreedores de 500 dólares. Este proyecto consistió en el desarrollo de una plataforma educativa con un módulo de asistencia para facilitar la comunicación entre alumnos y profesores.',
        color: 'green lighten-1',
        page: 'https://larepublica.pe/nota-de-prensa/2020/12/05/jovenes-arequipenos-obtuvieron-segundo-lugar-en-concurso-tecnologico-lrsd/',
        src: '/hackathon-apex.png',
        icon: 'mdi-vuejs'
      },
      {
        title: 'Hackathon ',
        subtitle: 'Ellos compitieron con el proyecto “DidacTICloud - Sistema Educativo Peruano”, que los hizo acreedores de 500 dólares. Este proyecto consistió en el desarrollo de una plataforma educativa con un módulo de asistencia para facilitar la comunicación entre alumnos y profesores.',
        color: 'indigo',
        page: 'https://larepublica.pe/nota-de-prensa/2020/12/05/jovenes-arequipenos-obtuvieron-segundo-lugar-en-concurso-tecnologico-lrsd/',
        src: '/hackathon-apex.png',
        icon: 'mdi-vuejs'
      }
    ],
    items: [
      {
        color: 'red lighten-2',
        icon: 'mdi-star'
      },
      {
        color: 'purple darken-1',
        icon: 'mdi-book-variant'
      },
      {
        color: 'green lighten-1',
        icon: 'mdi-airballoon'
      },
      {
        color: 'indigo',
        icon: 'mdi-buffer'
      }
    ]
  })
}
</script>
<style>
.image {
    background: url(https://fondosmil.com/fondo/17010.jpg );
    background-position: 50%;
    background-size: cover;
    background-repeat: no-repeat;
}
.image-carousels {
    background-position: 50%;
    background-size: cover;
    background-repeat: no-repeat;
}

/* @media screen and (max-width: 500px) { */
  .title-time-line {
    /* font-size: 14px; */
  white-space: pre-line;
 /* }  */
}
</style>
