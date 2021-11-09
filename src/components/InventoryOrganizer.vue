<template>
  <v-container class="mt-16" fluid>
    <v-row
        :class="{ 'flex-column-reverse': $vuetify.breakpoint.xs }"
        class="justify-center align-center d-flex"
    >
      <v-col class="pa-sm-16" cols="12" sm="7" style="left: 250px">
        <h1 class="mb-7">Система Інвентаризації</h1>
        <p>
          IO — це система інвентаризації розроблена для ведення електронного
          обліку обладнання та ліцензій програмного забезпечення на
          підприємстві.
        </p>
        <v-card-actions class="pa-0 justify-center justify-sm-start">
          <v-btn
              v-model="modal"
              v-bind="attrs"
              @click="dialogMethod"
              v-on="on"
              class="white--text rounded-lg"
              color="#7683F7"
              height="5vh"
              style="border-radius: 15px !important;"
              width="220px"
          >Увійти
          </v-btn>
        </v-card-actions>
      </v-col>
      <v-col cols="12" sm="5">
        <div class="io-img-container">
          <v-img contain src="../assets/IOB.svg" width="100%"></v-img>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "InventoryOrganizer",
  props: {
    modal: Boolean
  },
  methods: {
    dialogMethod() {
      if (this.dialog === false) {
        this.dialog = true;
      } else {
        this.dialog = false;
      }
    },
  },
};
</script>
<style scoped>
* {
  font-family: Nunito;
}

.container {
  background-color: rgba(217, 220, 245, 0.5);
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

.io-img-container {
  padding-right: 100px;
}

.rounded-lg {
  border-radius: 15px !important;
}

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
</style>
