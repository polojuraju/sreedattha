<template>
  <v-app id="inspire">
    <v-app-bar app color="white" flat id="scroll-target">
      <v-avatar size="56"
        ><img src="../assets/logo.jpg" alt="Sree Dattha" /> </v-avatar
      ><v-toolbar-title>Interio</v-toolbar-title>

      <!-- <v-toolbar-items right class="ml-n1" color="grey darken-1">
        <v-btn v-for="link in links" :key="link" text>
          {{ link }}
        </v-btn>
      </v-toolbar-items> -->

      <v-tabs class="ml-n1 tab-width" right>
        <v-tabs-slider color="yellow"></v-tabs-slider>
        <v-tab
          v-for="(link, i) in links"
          :key="i"
          @click="$vuetify.goTo(link.tab)"
        >
          {{ link.menu }}
        </v-tab>
      </v-tabs>
      <v-btn class="btn-quote" rounded color="primary" dark>
        Get A Quote
      </v-btn>
    </v-app-bar>
    <v-btn
      v-scroll="onScroll"
      v-show="fab"
      fab
      dark
      fixed
      bottom
      right
      color="primary"
      @click="toTop"
    >
      <v-icon>mdi-arrow-up</v-icon>
    </v-btn>
    <v-main>
      <section id="home">
         <v-layout column align-center justify-center class="white--text">
        <v-carousel>
          <v-carousel-item
            v-for="(item, i) in scrollImages" width="100%"
            :key="i"
            :src="item.backgroundImage"
            reverse-transition="fade-transition"
            transition="fade-transition"
          >
           
              <v-row class="fill-height" align="center" justify="center">
                <div class="text-h2">Slide {{ i + 1 }}</div>
              </v-row>
          
          </v-carousel-item>
        </v-carousel>
         </v-layout>
      </section>
      <!-- <section id="home">
        <v-parallax :src="imageLink.logo" height="600">
          <v-layout column align-center justify-center class="white--text">
            <h1
              class="white--text mb-2 display-1 text-xs-center"
              style="font-weight: 900; text-shadow: 3px 2px #000000"
            >
              The social network for epic content
            </h1>
            <div
              class="white--text subheading mb-3 text-xs-center"
              style="font-weight: 900; text-shadow: 2px 2px #000000"
            >
              Unlesh your creativity without limitations
            </div>
            <v-btn
              class="blue lighten-2 mt-5"
              dark
              large
              href="/pre-made-themes"
            >
              Get Started
            </v-btn>
          </v-layout>
        </v-parallax>
      </section> -->
      <section
        class="section-lg bg-white bg-img-custom"
        :style="cssProps"
        id="about"
      >
        <v-container>
          <v-layout wrap class="my-5">
            <v-row
              class="row justify-content-between row-60 row-md-30 flex-wrap-reverse flex-lg-wrap"
            >
              <v-col cols="7" sm="7"> </v-col>
              <v-col cols="5" sm="5">
                <div class="box-custom-2">
                  <h2 class="section-title">Why Choose Us</h2>
                  <p>
                    Besides great interior design, there are lots of reasons to
                    choose Interia. Here are some of the most popular ones.
                  </p>
                  <v-row>
                    <v-col>
                      <v-list-item
                        v-for="(item, i) in items"
                        :key="i"
                        cols="12"
                        class="unit-space index-list"
                      >
                        <v-list-item-icon class="icon-align">
                          <div
                            class="list-classic-rectangle"
                            color="primary"
                          ></div>
                          <v-icon large color=" darken-2" class="icon-lg">
                            mdi-domain
                          </v-icon>
                        </v-list-item-icon>
                        <v-list-item-content>
                          <v-list-item-title class="font-styles">{{
                            item.title
                          }}</v-list-item-title>
                          <v-list-item-subtitle class="content-align">
                            {{ item.content }}
                          </v-list-item-subtitle>
                        </v-list-item-content>
                      </v-list-item>
                      <div class="btn-align">
                        <v-btn class="btn-quote" rounded color="primary" dark>
                          Get A Quote
                        </v-btn>
                      </div>
                      <!-- <div class="d-flex flex-no-wrap justify-space-between">
                        <v-card-text>
                          <v-card-title>Professional Team</v-card-title>
                          Our team includes only the best decorators and
                          interior designers in the industry.
                        </v-card-text>
                      </div> -->
                    </v-col>
                  </v-row>
                </div>
              </v-col>
            </v-row>
          </v-layout>
        </v-container>
      </section>
      <section id="services">
        <h2 class="section-title">Our Services</h2>
        <v-container>
          <v-layout wrap class="my-5">
            <v-card
              class="mx-auto my-5"
              max-width="344"
              v-for="(item, i) in services"
              :key="i"
            >
              <v-img
                src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
                height="300px"
              ></v-img>

              <v-card-title> {{ item.title }} </v-card-title>
              <v-card-text>
                {{ item.content }}
              </v-card-text>
            </v-card>
          </v-layout>
        </v-container>
      </section>
      <section id="portfolio">
        <h2 class="section-title">WHAT PEOPLE SAY</h2>
        <v-container>
          <v-layout wrap class="my-5">
            <v-carousel>
              <v-carousel-item>
                <v-row class="people-say">
                  <v-card class="mx-auto" max-width="300">
                    <v-card-title>
                      <v-icon large left> mdi-twitter </v-icon>
                      <span class="text-h6 font-weight-light">Twitter</span>
                    </v-card-title>

                    <v-card-text>
                      "Turns out semicolon-less style is easier and safer in TS
                      because most gotcha edge cases are type invalid as well."
                    </v-card-text>
                  </v-card>
                  <v-card class="mx-auto" max-width="300">
                    <v-card-title>
                      <v-icon large left> mdi-twitter </v-icon>
                      <span class="text-h6 font-weight-light">Twitter</span>
                    </v-card-title>

                    <v-card-text>
                      "Turns out semicolon-less style is easier and safer in TS
                      because most gotcha edge cases are type invalid as well."
                    </v-card-text>
                  </v-card>
                  <v-card class="mx-auto" max-width="300">
                    <v-card-title>
                      <v-icon large left> mdi-twitter </v-icon>
                      <span class="text-h6 font-weight-light">Twitter</span>
                    </v-card-title>

                    <v-card-text>
                      "Turns out semicolon-less style is easier and safer in TS
                      because most gotcha edge cases are type invalid as well."
                    </v-card-text>
                  </v-card>
                </v-row>
              </v-carousel-item>
            </v-carousel>
          </v-layout>
        </v-container>
      </section>
    </v-main>
    <v-footer dark padless>
      <v-card flat tile class="lighten-1 white--text text-center">
        <v-card-text>
          <v-btn
            v-for="(social, i) in socials"
            :key="i"
            class="mx-4 white--text"
            :color="social.color"
            icon
          >
            <v-icon size="24px">
              {{ social.icon }}
            </v-icon>
          </v-btn>
        </v-card-text>

        <v-card-text class="white--text pt-0">
          Phasellus feugiat arcu sapien, et iaculis ipsum elementum sit amet.
          Mauris cursus commodo interdum. Praesent ut risus eget metus luctus
          accumsan id ultrices nunc. Sed at orci sed massa consectetur dignissim
          a sit amet dui. Duis commodo vitae velit et faucibus. Morbi vehicula
          lacinia malesuada. Nulla placerat augue vel ipsum ultrices, cursus
          iaculis dui sollicitudin. Vestibulum eu ipsum vel diam elementum
          tempor vel ut orci. Orci varius natoque penatibus et magnis dis
          parturient montes, nascetur ridiculus mus.
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text class="white--text">
          © {{ new Date().getFullYear() }}
          <strong>Sree Dattha CNC Crafts & Interio</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
import logo from "../assets/img.jpeg";
import backgroundImage from "../assets/image-1.jpg";
export default {
  data: () => ({
    scrollImages: [
      {
        backgroundImage: backgroundImage,
      },
      {
        backgroundImage: `url(${require("@/assets/home.png")})`,
      },
      {
        backgroundImage: `url(${require("@/assets/image-1.jpg")})`,
      },
    ],
    cssProps: {
      backgroundImage: `url(${require("@/assets/home.png")})`,
    },
    tab: null,
    fab: false,
    model: 0,
    links: [
      {
        menu: "Home",
        tab: "#home",
      },
      {
        menu: "About",
        tab: "#about",
      },
      {
        menu: "Portfolio",
        tab: "#services",
      },
      { menu: "Contact", tab: "#contact" },
    ],
    imageLink: {
      logo: logo,
      backgroundImage: backgroundImage,
    },
    icons: ["mdi-facebook", "mdi-twitter", "mdi-linkedin", "mdi-instagram"],
    socials: [
      {
        icon: "mdi-facebook",
        color: "indigo",
      },
      {
        icon: "mdi-linkedin",
        color: "cyan darken-1",
      },
      {
        icon: "mdi-instagram",
        color: "red lighten-3",
      },
    ],
    items: [
      {
        title: "Professional Team",
        content:
          "Our team includes only the best decorators and interior designers in the industry.",
      },
      {
        title: "Unusual Ideas",
        content:
          "Our designers generate various yet always original ideas that will surely fit your needs.",
      },
      {
        title: "Professional Team",
        content:
          "Our team includes only the best decorators and interior designers in the industry.",
      },
      {
        title: "Unusual Ideas",
        content:
          "Our designers generate various yet always original ideas that will surely fit your needs.",
      },
    ],
    services: [
      {
        title: "Modular Kitchens",
        content:
          "Modular kitchen is a new and innovative solution to the challenges posed by traditional kitchens. Functional and durable, it  makes everyday kitchen tasks easy to manage.",
      },
      {
        title: "Living Rooms",
        content:
          "Modular kitchen is a new and innovative solution to the challenges posed by traditional kitchens. Functional and durable, it  makes everyday kitchen tasks easy to manage. ",
      },
      {
        title: "Bed Rooms",
        content:
          "Modular kitchen is a new and innovative solution to the challenges posed by traditional kitchens. Functional and durable, it  makes everyday kitchen tasks easy to manage. ",
      },
      {
        title: "TV Unit",
        content:
          "Modular kitchen is a new and innovative solution to the challenges posed by traditional kitchens. Functional and durable, it  makes everyday kitchen tasks easy to manage. ",
      },
      {
        title: "False Celing",
        content:
          "Modular kitchen is a new and innovative solution to the challenges posed by traditional kitchens. Functional and durable, it  makes everyday kitchen tasks easy to manage. ",
      },
      {
        title: "CNC Works",
        content:
          "Modular kitchen is a new and innovative solution to the challenges posed by traditional kitchens. Functional and durable, it  makes everyday kitchen tasks easy to manage. ",
      },
    ],
  }),
  methods: {
    onScroll(e) {
      if (typeof window === "undefined") return;
      const top = window.pageYOffset || e.target.scrollTop || 0;
      this.fab = top > 20;
    },
    toTop() {
      this.$vuetify.goTo(0);
    },
  },
};
</script>
