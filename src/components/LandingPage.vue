<template>
    <v-section> 
        <VideoParallax :src="video" height="600" width="100%">
          <v-layout column align-center justify-center class="white--text">
            <v-btn class="imageMain">
              Get Started
            </v-btn>
          </v-layout>
        </VideoParallax>
        <v-layout column align-center justify-center>
            <v-flex xs12 sm4>
                <h2 class="headline">The best way to share my amazing experience</h2>
                <span class="subheading">
                    No more restrictions, no more limits
                </span>
            </v-flex>            
        </v-layout>
        <v-carousel>
            <v-carousel-item>
            <v-layout column align-center justify-center>
                <v-layout column align-center style="padding-top:50px">
                    <v-row>
                        <v-col cols="12" md="4">
                            <v-card>
                                <v-img :src="image.indigo" width="250" height="200" class="img"> </v-img>
                                <v-card-title primary-title style="justify-content:center"> 
                                    <h3> INDIGO CREATIVE NATION </h3>
                                </v-card-title>
                                <v-card-text>
                                    Rebuild admin site indigo with new technology.
                                    using node.js and vue.js
                                </v-card-text>
                            </v-card>
                        </v-col>
                        <v-col cols="12" md="4">
                            <v-card>
                                <v-img :src="image.korsabhara" width="160" class="img" height="200"> </v-img>
                                <v-card-title primary-title style="justify-content:center"> 
                                    <h3 class="content"> KORSABHARA </h3>
                                </v-card-title>
                                <v-card-text>
                                    Building dashboard using apache superset and maintenance application
                                    using node.js and vue.js
                                </v-card-text>
                            </v-card>
                        </v-col>
                        <v-col cols="12" md="4">
                            <v-card>
                                <v-img :src="image.korlantas" width="160" class="img" height="200"> </v-img>
                                <v-card-title primary-title style="justify-content:center"> 
                                    <h3 class="content"> KORLANTAS </h3>
                                </v-card-title>
                                <v-card-text>
                                    Building dashboard using qlik sense and maintenance application
                                    using node.js and vue.js
                                </v-card-text>
                            </v-card>
                        </v-col>
                    </v-row>
                </v-layout>
            </v-layout>
        </v-carousel-item>
        <v-carousel-item>
            <v-layout column align-center justify-center>
            <v-layout row wrap align-center style="padding-top:50px"> 
            <v-row>
                <v-col cols="12" md="4">
                        <v-card height="345px" width="800px">
                            <v-img :src="image.bsp" width="350" class="img" height="200"> </v-img>
                            <v-card-title primary-title style="justify-content:center"> 
                                <h3 class="content"> BSP Face Detection </h3>
                            </v-card-title>
                            <v-card-text>
                                Building application for attendance with face detection for
                                checkin and checkout using node.js and vue.js
                            </v-card-text>
                        </v-card>
                    </v-col>
                    <v-col cols="12" md="4">
                        <v-card height="345px">
                            <v-img :src="image.bsp" width="350" class="img" height="200"> </v-img>
                            <v-card-title primary-title style="justify-content:center"> 
                                <h3 class="content"> BSP Company Profile </h3>
                            </v-card-title>
                            <v-card-text>
                                Building website company profile using node.js and vue.js
                            </v-card-text>
                        </v-card>
                    </v-col>
                </v-row>
                </v-layout>
                </v-layout>
            </v-carousel-item>
        </v-carousel>
    </v-section>
</template>

<script>
import imageMain from '../assets/physics.jpg'
import imageSocial from '../assets/physics3.jpg'
import IndigoTelkom from '../assets/indigo.png'
import Korsabhara from '../assets/Korsabhara.jpg'
import Korlantas from '../assets/korlantas.jpg'
import BSP from '../assets/logo_bsp.png'
import VideoURL from '../assets/physics.mp4'
import VideoParallax from 'vuetify-video-parallax';

export default {
    name: 'LandingPage',
    components: {
        VideoParallax,
    },
    data() {
        return {
            image: {
                main: imageMain,
                socialCover: imageSocial,
                indigo: IndigoTelkom,
                korsabhara: Korsabhara,
                korlantas: Korlantas,
                bsp: BSP
            },
            video: VideoURL
        }
    },
    methods: {
        downloadFile() {
        const me = this;
        fetch(me.file)
            .then((resp) => resp.blob())
            .then((blob) => {
            const url = window.URL.createObjectURL(blob);
            const a = document.createElement("a");
            a.style.display = "none";
            a.href = 'CV.pdf'
            // the filename you want
            a.download = me.name || "cv-riska.pdf";
            document.body.appendChild(a);
            a.click();
            window.URL.revokeObjectURL(url);
            alert("your file has downloaded!");
            })
            .catch(() => alert("oh no!"));
        },
    }
}

</script>

<style scoped>
    .curaousel {
        margin-left: 30%;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        font-size: x-large;
    }
    .subheading {
        margin-left: 90px;
        font-family: 'Courier New', Courier, monospace;
    }
    .content {
        text-align: center;
    }
    .img {
        display: block;
        margin-left: auto;
        margin-right: auto;
    }
    h3 {
        color: #ccc;
        background-color: black;
    }
</style>

