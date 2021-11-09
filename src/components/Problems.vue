<template>
  <div class="text-center">
    <h1 class="my-14">Проблеми</h1>
    <v-parallax
        class="content d-flex justify-center align-center"
        style="background: linear-gradient(top right, rgba(67, 84, 242, 0.5), rgba(67, 84, 242, 0.5))"
          src="../assets/image.png"
    >
        <p class="px-16">
          Система дозволяє зберігання інформації про обладнання та програмне
          забезпечення, збереження історії про ремонти, передачі, списання та
          утилізації обладнання, формування звітів. Не потребує встановлення на
          персональний комп’ютер.
        </p>
    </v-parallax>
  </div>
</template>

<script>
export default {
  name: "Problems",
  data: () => ({}),
};
</script>

<style scoped>
h1 {
  font-family: "Nunito";
  color: #00084d;
  font-size: 48px;
}

.content {
  color: white;
  font-family: Nunito;
  font-style: normal;
  font-weight: 900;
  font-size: 22px;
}
</style>
