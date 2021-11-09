<template>
  <v-container class="mainBlock mt-16" fluid>
    <v-container>
      <h1 class="block-title mb-12">Робота з нами</h1>
      <div class="d-flex justify-center">
        <table style="border-collapse: collapse">
          <tr>
            <td
                v-for="(item, index) in items"
                :key="index"
                style="vertical-align: top"
            >
              <div v-if="item.top" class="item-text">
                {{ item.text }}
              </div>
            </td>
          </tr>
          <tr>
            <td
                v-for="(item, index) in items"
                :key="index"
                style="vertical-align: top"
            >
              <div v-if="item.top" class="item-figure item-figure-top">
                {{ item.number | twoDigits }}
              </div>
            </td>
          </tr>

          <tr>
            <td
                v-for="(item, index) in items"
                :key="index"
                style="vertical-align: top"
            >
              <div v-if="!item.top" class="item-figure item-figure-bottom">
                {{ item.number | twoDigits }}
              </div>
            </td>
          </tr>

          <tr>
            <td
                v-for="(item, index) in items"
                :key="index"
                style="vertical-align: top"
            >
              <div v-if="!item.top" class="item-text">
                {{ item.text }}
              </div>
            </td>
          </tr>
        </table>
      </div>
    </v-container>
  </v-container>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      items: [
        {
          text: "Внесення накладних з обладнанням та ліцензіями",
          number: 1,
          top: true,
        },
        {
          text: "Перегляд предметів та приміщення у якому їх встановлено ",
          number: 2,
          top: false,
        },
        {
          text: "Перегляд предметів та їх власників",
          number: 3,
          top: true,
        },
        {
          text: "Перегляд обладнання з індивідуальними QR-кодами",
          number: 4,
          top: false,
        },
        {
          text: "Передача обладнання між власникам",
          number: 5,
          top: true,
        },
        {
          text: "Відправлення обладнання у ремонт",
          number: 6,
          top: false,
        },
        {
          text: "Списання обладнання",
          number: 7,
          top: true,
        },
        {
          text: "Утилізація обладнання",
          number: 8,
          top: false,
        },
      ],
    };
  },
  filters: {
    twoDigits: (value) => {
      if (value.toString().length === 1) {
        return `0${value}`;
      }
      return value;
    },
  },
};
</script>

<style scoped>
* {
  font-family: "Nunito";
}

h1 {
  text-align: center;
  color: #00084d;
  font-size: 48px;
}

.mainBlock {
  background: url("../assets/img.svg") no-repeat center;
  min-height: 645px;
}

.item-figure-top {
  position: relative;
  bottom: -1px;
  background: url("../assets/figureTop.svg") no-repeat center;
}

.item-figure-bottom {
  position: relative;
  top: -1px;
  background: url("../assets/figureDown.svg") no-repeat center;
}

.item-figure {
  width: 180px;
  text-align: center;
  font-style: normal;
  font-weight: bold;
  color: #ffffff;
  line-height: 1.25;
  font-size: 68px;
  min-height: 89px;
}

.item-text {
  width: 180px;
  font-style: normal;
  font-weight: normal;
  font-size: 18px;
  line-height: 25px;

  color: #000000;
}
</style>
