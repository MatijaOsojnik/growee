<template>
  <v-app style="background-color: #f9f7f7" light>
    <Navbar></Navbar>

    <svg
      xmlns="http://www.w3.org/2000/svg"
      preserveAspectRatio="none"
      style="width:100%;height:14rem;display:block;margin-top: -2rem"
      viewBox="0 0 1440 320"
    >
      <path
        fill="#617be3"
        fill-opacity="1"
        d="M0,96L48,90.7C96,85,192,75,288,74.7C384,75,480,85,576,96C672,107,768,117,864,133.3C960,149,1056,171,1152,170.7C1248,171,1344,149,1392,138.7L1440,128L1440,0L1392,0C1344,0,1248,0,1152,0C1056,0,960,0,864,0C768,0,672,0,576,0C480,0,384,0,288,0C192,0,96,0,48,0L0,0Z"
      />
    </svg>

    <v-container fluid style="z-index:1">
      <v-container>
        <!-- HEADER -->

        <v-row>
          <v-col md="7" lg="5" sm="12" cols="12">
            <v-layout column justify-center align-center>
              <v-flex>
                <h2 class="heading">
                  Best
                  <span class="heading" style="color:#4f81c7">Market Analytics</span> AI Ever.
                </h2>
                <h5
                  class="subheading"
                  style="padding-bottom: 2rem;"
                >Let us get your business ahead of your competition in no-time with the help of marketing automation.</h5>
                <v-form :lazy-validation="lazy" ref="form">
                  <v-row>
                    <v-col md="7">
                      <v-text-field
                        label="Your Business Name"
                        v-model="businessName"
                        outlined
                        rounded
                      />
                    </v-col>
                    <v-col class="text-sm-left text-md-left" md="5">
                      <v-btn height="55px" color="#4f81c7" class="white--text" to="/pricing">
                        <span style="font-size: 15px; padding-right: 5px;">Analyze Market</span>
                      </v-btn>
                    </v-col>
                  </v-row>
                </v-form>
              </v-flex>
            </v-layout>
          </v-col>
          <v-col
            class="text-center column align-content-center align-self-center justify-center"
            md="5"
            lg="7"
            sm="12"
            cols="12"
          >
            <v-flex>
              <img src="~/assets/datatrends.svg" height="70%" width="60%" />
            </v-flex>
          </v-col>
        </v-row>
      </v-container>
    </v-container>

    <!-- BODY -->
    <svg
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 1440 320"
      style="transform: rotate(90deg);position:absolute;margin-left:100vw;"
    >
      <path
        fill="#575A89"
        fill-opacity="0.3"
        d="M0,224L80,213.3C160,203,320,181,480,160C640,139,800,117,960,122.7C1120,128,1280,160,1360,176L1440,192L1440,0L1360,0C1280,0,1120,0,960,0C800,0,640,0,480,0C320,0,160,0,80,0L0,0Z"
      />
    </svg>
    <!-- FEATURES -->
    <v-container fluid>
      <v-container>
        <v-layout row justify>
          <v-flex class="row">
            <v-row v-for="(item, index) in features" :key="index">
              <CardFeature :img="item.img" :title="item.title" :text="item.text"></CardFeature>
            </v-row>
          </v-flex>
        </v-layout>
      </v-container>
    </v-container>

    <!-- FUNCTIONS -->
    <v-container fluid>
      <v-container>
        <h1
          class="display-1"
          align="center"
          style="font-weight:700;padding:0;margin:0 13px 10rem 0;"
        >The Platform You Need</h1>
        <v-layout row justify class="mx-12">
          <v-flex class="row">
            <v-row v-for="(item, index) in functions" :key="index">

              <FunctionComponent class="hidden-sm-and-down" v-if="index%2===0" :img="item.img" :title="item.title" :text="item.text"></FunctionComponent>
              <ReverseFunctionComponent class="hidden-sm-and-down" v-if="index%2===1" :img="item.img" :title="item.title" :text="item.text"></ReverseFunctionComponent>
              <ReverseFunctionComponent class="hidden-md-and-up" :img="item.img" :title="item.title" :text="item.text"></ReverseFunctionComponent>
              
            </v-row>
          </v-flex>
        </v-layout>
      </v-container>
    </v-container>


    <!-- FOOTER -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320" preserveAspectRatio="none" style="width:100%;height:14rem;display:block;margin-top: -2rem"><path fill="#617be3" fill-opacity="1" d="M0,256L48,250.7C96,245,192,235,288,213.3C384,192,480,160,576,165.3C672,171,768,213,864,208C960,203,1056,149,1152,144C1248,139,1344,181,1392,202.7L1440,224L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path></svg>    
<Footer></Footer>

  </v-app>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import CardFeature from "@/components/CardFeature.vue";
import Footer from "@/components/Footer.vue";
import FunctionComponent from "@/components/FunctionComponent.vue";
import ReverseFunctionComponent from "@/components/ReverseFunctionComponent.vue";
import {showAt, hideAt} from 'vue-breakpoints';
export default {
  components: {
    Navbar,
    CardFeature,
    FunctionComponent,
    ReverseFunctionComponent,
    hideAt,
    showAt,
    Footer
  },
  data: () => ({
    lazy: true,
    features: [
      {
        img: "artificial-intelligence.svg",
        title: "Advanced AI",
        text:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Lorem sed risus ultricies tristique nulla aliquet enim. "
      },
      {
        img: "research.svg",
        title: "SEO Service",
        text:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Lorem sed risus ultricies tristique nulla aliquet enim. "
      },
      {
        img: "computer.svg",
        title: "Website Design",
        text:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Lorem sed risus ultricies tristique nulla aliquet enim."
      }
    ],
    functions: [
      {
        img: "datapoints.svg",
        title: "Market Research",
        text:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Lorem sed risus ultricies tristique nulla aliquet enim. "
      },
            {
        img: "uptodate.svg",
        title: "SEO Service",
        text:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Lorem sed risus ultricies tristique nulla aliquet enim. "
      },
            {
        img: "dashboard.svg",
        title: "Beautiful Dashboard",
        text:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Lorem sed risus ultricies tristique nulla aliquet enim. "
      }
    ]
  }),
  props: {
    businessName: ""
  }
};
</script>

<style>
h3 {
  color: #333333;
  padding: 0.3rem;
}
.cta-lower {
  color: #bbbbbb;
  font-size: 12px;
  padding-right: 5px;
  text-transform: none;
}
.heading {
  padding: 0 0 2rem;
  font-size: 42px;
  font-weight: 800;
  color: #2f2e41;
}
.subheading {
  padding-bottom: 2rem;
  font-size: 19px;
  font-weight: 700;
  color: #6c7b95;
  letter-spacing: 0.7px;
}
.description {
  margin-top: 4rem;
  font-size: 19px;
  color: #2d334a;
  letter-spacing: 1.3px;
  font-weight: 500;
}
</style>
