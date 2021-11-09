<template>
  <v-app id="inspire">
    <Navbar/>
    <InventoryOrganizer/>
    <WorkWithUs/>
    <Problems/>
    <h1 class="block-title ma-10 d-flex justify-center">Переваги</h1>
    <Benefits/>
    <div>
      <GetAccess/>
    </div>
    <Footer/>
  </v-app>
</template>


<script>
import Navbar from "./components/Navbar";
import InventoryOrganizer from "./components/InventoryOrganizer";
import Benefits from "./components/Benefits";
import WorkWithUs from "./components/WorkWithUs";
import Problems from "./components/Problems";
import GetAccess from "./components/GetAccess";
import Footer from "./components/Footer";

export default {
  components: {
    Navbar,
    InventoryOrganizer,
    Benefits,
    WorkWithUs,
    Problems,
    GetAccess,
    Footer,
  },
  data: () => ({
    modal: false,
  }),
  methods: {
    setModal(modal) {
      this.modal = modal;
    },
  },
  name: "App",
};
</script>


<style scoped>
h1 {
  font-family: "Nunito";
  color: #00084d;
  font-size: 48px;
}
</style>
