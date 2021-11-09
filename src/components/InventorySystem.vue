<template>
  <div class="main d-flex align-center">
    <div class="content">
      <h1>Система Інвентаризації</h1>
      <p>
        IO — це система інвентаризації розроблена для ведення електронного
        обліку обладнання та ліцензій програмного забезпечення на підприємстві.
      </p>
      <button @click.stop="dialog = true">Увійти</button>
    </div>
    <div class="image">
      <img src="../assets/QR.png" />
    </div>

    <v-dialog v-model="dialog">
      <v-card>
        <div class="dialog-content">
          <img src="../assets/footer_logo.png" />

          <div class="head-btn">
            <v-btn class="btn" text @click="dialog = false">
              <v-icon large left> mdi-google-plus </v-icon>
              Google
            </v-btn>

            <v-btn class="btn ml-4" text @click="dialog = false">
              <v-icon large left> mdi-microsoft-windows </v-icon>
              Microsoft</v-btn
            >
          </div>

          <div class="title">
            <span> або </span>
          </div>
          <div class="input text-center">
            <input type="text" placeholder="Ваша пошта" />
          </div>

          <v-btn class="sigin" text @click="dialog = false"> Увійти </v-btn>

          <div class="dialog-footer">Всі права захищено © IO 2021</div>
        </div>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  name: "InventorySystem",
  data() {
    return {
      dialog: false,
    };
  },
};
</script>

<style scoped>
button {
  width: 220px;
  height: 50px;
  cursor: pointer;
  background: #7683f7;
  border-radius: 15px;
  color: white;
  font-family: Nunito;
  font-style: normal;
  font-weight: bold;
  font-size: 18px;
}

.main {
  font-family: "Nunito";
  width: 100%;
  height: 100%;
  background-color: #d9dcf580;
  height: 800px;
}

h1 {
  font-style: normal;
  font-weight: bold;
  font-size: 42px;
  line-height: 57px;
  color: #000000;
  margin-bottom: 30px;
}

p {
  font-style: normal;
  font-weight: normal;
  font-size: 36px;
  line-height: 49px;
  align-items: center;
  color: #000000;
  margin-bottom: 30px;
}

.content {
  margin-left: 241px;
  max-width: 831px;
}
.v-dialog {
  overflow-y: hidden;
}
.dialog-content {
  background: rgba(255, 255, 255, 0.3);
  border-radius: 15px;
}

.v-card {
  background: linear-gradient(282.65deg, #7683f7 0%, #dde0ff 99.33%);
  backdrop-filter: blur(50px);
  border-radius: 15px;
  justify-content: center;
  text-align: center;
}

.sigin {
  width: 220px;
  height: 50px;
  background: #7683f7;
  border-radius: 10px;
  color: white;
  margin: 50px 0 128px 0;
}

.dialog-content .btn {
  width: 250px;
  height: 70px;
  background: none;
  border: 3px solid #484bf2;
  border-radius: 15px;
  padding: 15px;
}
.head-btn {
  margin-bottom: 60px;
}
.dialog-content img {
  margin-bottom: 85px;
  margin-top: 32px;
  width: 300px;
}

.btn .v-icon {
  color: #484bf2;
  margin-right: 20px;
}
.image {
  width: 300px;
}

.btn:hover .v-icon {
  color: #ff725e;
}

.btn:hover {
  border: 3px solid #ff725e;
}

.title {
  overflow: hidden;

  text-align: center;
  /* Тут можно добавить другие стили для заголовка */
  font-size: 18px;
  margin-bottom: 95px;
}
.title span {
  font-family: Nunito;
  color: #484bf2;

  display: inline-block;
  vertical-align: middle;
}
.title:before,
.title:after {
  content: "";

  display: inline-block;
  vertical-align: middle;

  width: 344px;
  height: 1px;

  background-color: #484bf2;

  position: relative;
}
.title:before {
  margin-left: -100%;

  left: -14px;
}
.title:after {
  margin-right: -100%;

  right: -14px;
}

.v-text-field {
  text-align: center;
  width: 600px;
}

input {
  width: 550px;
  height: 60px;
  border: 3px solid #7683f7;
  border-radius: 15px;
  padding: 15px;
}

input:hover {
  border: 3px solid #ff725e;
}

.dialog-footer {
  padding: 20px 0;
}
.image {
  margin-left: -200px;
}
</style>