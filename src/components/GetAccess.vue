<template>
  <v-container class="mt-16 pb-16" fluid>
    <v-row>
      <v-col cols="12" md="6" sm="12">
        <v-card
          class="card mb-4 mx-auto d-flex justify-center align-center"
          elevation="12"
          height="250"
          src="../assets/logo.svg"
        >
          <img src="../assets/Frame 14.png" />
          <div class="content d-flex justify-center align-center">
            <div>
              <h4>Ігор Зубенко</h4>
              <div class="mt-4">
                <a href="#">
                  <v-icon> mdi-email </v-icon>
                </a>
                <a class="ml-4" href="#"><v-icon> mdi-facebook </v-icon> </a>
              </div>
            </div>
          </div>
        </v-card>

        <v-card
          class="card mb-4 mx-auto d-flex justify-center align-center"
          elevation="12"
          height="250"
        >
          <img src="../assets/Frame 13.png" />
          <div class="content d-flex justify-center align-center">
            <div>
              <h4>Максим Луцюк</h4>

              <div class="mt-4">
                <a href="#">
                  <v-icon> mdi-email </v-icon>
                </a>
                <a class="ml-4" href="#"><v-icon> mdi-facebook </v-icon> </a>
              </div>
            </div>
          </div>
        </v-card>

        <v-card
          class="card mb-4 mx-auto d-flex justify-center align-center"
          elevation="12"
          height="250"
        >
          <img src="../assets/Frame 15.png" />
          <div class="content d-flex justify-center align-center">
            <div>
              <h4>Анна Романюк</h4>

              <div class="mt-4">
                <a href="#">
                  <v-icon> mdi-email </v-icon>
                </a>
                <a class="ml-4" href="#"><v-icon> mdi-facebook </v-icon> </a>
              </div>
            </div>
          </div>
        </v-card>
      </v-col>

      <v-col cols="12" md="6" sm="12" lg="6" xl="4">
        <div class="d-flex justify-center">
          <div class="form text-center">
            <h1>Отримати доступ</h1>
            <form>
              <v-text-field label="П.І.Б"></v-text-field>
              <v-text-field label="Назва організації"></v-text-field>
              <v-text-field label="Email"></v-text-field>
              <v-text-field label="Телефон"></v-text-field>
              <v-textarea
                name="input"
                filled
                label="Повідомлення"
                auto-grow
              ></v-textarea>
              <button type="submit">Отримати доступ</button>
            </form>
          </div>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "GetAccess",
  data: () => ({}),
};
</script>

<style scoped>
.container img {
  width: 100%;
  height: 100%;
}

.container {
  font-family: Nunito;
  background: url("../assets/background.png") no-repeat center center;
  background-size: cover;
}

.container .v-card {
  max-width: 600px;
  border-radius: 15px;
}

.content {
  color: white;
  height: 100%;
  width: 70%;
  background: url("../assets/Rectangle 52.png") no-repeat center center;
  position: absolute;
  left: 40%;
}

@media screen and (max-width: 600px) {
  .content {
    display: none;
    left: 40% - 5%;
  }
}

.content a {
  text-decoration: none;
}

.form {
  width: 85%;
}

.content .v-icon {
  background: none;
  border-radius: 50%;
  border: 2px solid #ffb27d;
  padding: 10px;
  color: #ffb27d;
}

h1 {
  color: #00084d;
  font-size: 48px;
}

button {
  width: 220px;
  height: 60px;
  cursor: pointer;
  background: #7683f7;
  border-radius: 15px;
  color: white;
  font-style: normal;
  font-weight: bold;
  font-size: 18px;
}
</style>
