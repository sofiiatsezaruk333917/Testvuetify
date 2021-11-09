<template>
    <v-item-group class="justify-center">
      <div class="text--primary">
        <v-hover>
          <div class="cards">
            <img src="../assets/fon.png"
                 class="fonts pa-0 ml-8 justify-center "

            />
            <v-row align="center" no-gutters>
              <v-card
                  class="card pa-16 mt-16 mx-3 transition-swing rounded-lg justify-center scale"
                  :class="`elevation-${hover ? 24:12}`"
                  color="#FFFFFF"
                  width="100%"
                  height="60%"

              >
                <img
                    class="pa-4 "
                    src="../assets/img1.png"
                    alt=""
                >
                <div class="content">
                  <p
                      class="pa-3 mx-n14 text-center"
                  >
                    Легкий перегляд пов’язаної інформації у одному місці</p>
                </div>
              </v-card>
            </v-row>
            <v-row align="center" no-gutters>
              <v-card
                  class="card pa-16 mt-16 mx-3 transition-swing rounded-lg justify-center scale"
                  :class="`elevation-${hover ? 24 : 12}`"
                  color="#FFFFFF"
                  width="100%"
                  height="60%"
              >
                <img
                    class="pa-4"
                    src="../assets/img2.png"
                    alt=""
                >
                <div class="content">
                  <p
                      class="pa-4 mx-n14 text-center"
                  >
                    Простий інтерфейс у стилі material design</p>
                </div>
              </v-card>
            </v-row>
            <v-row align="center" no-gutters>
              <v-card
                  class="card pa-16 mt-16 mx-3 transition-swing rounded-lg justify-center scale"
                  :class="`elevation-${hover ? 24 : 12}`"
                  color="#FFFFFF"
                  width="100%"
                  height="60%"
              >
                <img
                    class="pa-4"
                    src="../assets/img3.png"
                    alt=""
                >
                <div class="content">
                  <p
                      class="pa-3 mx-n14 text-center"
                  >
                    Швидка авторизація через Google OAuth 2.0</p>
                </div>
              </v-card>
            </v-row>
            <v-row align="center" no-gutters>
              <v-card
                  class="card pa-16 mt-16 mx-3 transition-swing rounded-lg justify-center scale"
                  :class="`elevation-${hover ? 24 : 12}`"
                  color="#FFFFFF"
                  width="100%"
                  height="60%"
              >
                <img
                    class="pa-4"
                    src="../assets/img4.png"
                    alt=""
                >
                <div class="content">
                  <p
                      class="pa-3 mx-n14 text-center"
                  >
                    Доступ з будь-якого сучасного веб-браузера</p>
                </div>
              </v-card>
            </v-row>
            <v-row align="center" no-gutters>
              <v-card
                  class="card pa-16 mt-16 mx-3 transition-swing rounded-lg justify-center scale"
                  :class="`elevation-${hover ? 24 : 12}`"
                  color="#FFFFFF"
                  width="100%"
                  height="60%"
              >
                <img
                    class="pa-4"
                    src="../assets/img5.png"
                    alt=""
                >
                <div class="content">
                  <p
                      class="pa-2 mx-n14 text-center"
                  >
                    Інтеграція з Google Workspace</p>
                </div>
              </v-card>
            </v-row>
          </div>
          <!--              </template>-->
        </v-hover>
      </div>
    </v-item-group>
</template>

<script>
export default {
  name: "Benefits",

  data() {
    return {
      tinySliderOptions: {
        mouseDrag: true,
        gutter: 20,
        swipeAngle: 45,
        controls: false,
        autoplay: false,
        items: 5,
        autoplayButtonOutput: false,
        freezable: false,
      },
    };
  },
};
</script>
<style>
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(14%, 1fr));
  grid-gap: 2%;
}

.cards {
  display: grid;
  left: 50%;
}

.cards img {
  object-fit: cover;
  width: 100%;
  height: 100%;
}

.scale:hover {
  transform: scale(1.2);
}

.fonts {
  position: absolute;
  width: 74%;
  height: 30%;
  left: 10%;
  top: 5%;
}

.titel {
  font-family: "Nunito", sans-serif;
  font-style: normal;
  font-weight: normal;
  font-size: 50px;
  line-height: 65px;
  color: #00084d;
}

.content {
  font-family: "Nunito", sans-serif;
  font-style: normal;
  font-weight: normal;
  font-size: 100%;
  line-height: 100%;
  text-align: center;
  color: #000000;
}
</style>
