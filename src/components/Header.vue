<template>
  <v-toolbar>
    <v-toolbar-title> <img src="../assets/footer_logo.png" /></v-toolbar-title>
    <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-sm-and-down align-center">
      <button
        class="btn"
        v-for="item in menu"
        :key="item.title"
        :to="item.link"
      >
        {{ item.title }}
      </button>
      <div class="d-flex align-center">
        <button class="LogIn">Увійти</button>
      </div>
    </v-toolbar-items>
    <v-menu class="hidden-md-and-up">
      <v-toolbar-side-icon slot="activator"></v-toolbar-side-icon>
      <v-list>
        <v-list-tile v-for="item in menu" :key="item.icon">
          <v-list-tile-content>
            <v-list-tile-title>{{ item.title }}</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-menu>
  </v-toolbar>
</template>

<script>
export default {
  data() {
    return {
      menu: [
        { title: "Робота з нами" },
        { title: "Проблеми" },
        { title: "Переваги" },
        { title: "Команда" },
      ],
    };
  },

  methods: {
    menuItems() {
      return this.menu;
    },
  },
};
</script>

<style scoped>
button {
  font-family: Nunito;
  font-style: normal;
  font-weight: normal;
  font-size: 18px;
  width: 220px;
  height: 50px;
  box-shadow: none;
}
.LogIn {
  background: #7683f7;
  border-radius: 15px;
  color: white;
  margin: 0 10px;
}

.v-toolbar img {
  width: 153px;
  margin: 9px 0 9px 236px;
  padding: 10px;
  background: none;
}
</style>
