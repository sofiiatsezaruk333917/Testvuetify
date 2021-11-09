
<template>
  <div class="pa-6">
    <v-data-table
      :headers="headers"
      :items="items"
      :search="search"
      sort-by="dateBirth"
      class="elevation-1 about pa-6"
    >
      <template v-slot:top>
        <v-toolbar flat>
          <v-toolbar-title>
            <v-text-field
              v-model="search"
              append-icon="mdi-magnify"
              label="Search"
              single-line
              hide-details
            ></v-text-field>
          </v-toolbar-title>
          <!-- <v-divider class="mx-4" inset vertical></v-divider> -->
          <v-spacer></v-spacer>
          <v-dialog v-model="dialog" max-width="500px">
            <template v-slot:activator="{ on, attrs }">
              <v-btn color="primary" dark class="mb-2" v-bind="attrs" v-on="on">
                New Item
              </v-btn>
            </template>
            <v-card>
              <v-card-title>
                <span class="text-h5">{{ formTitle }}</span>
              </v-card-title>

              <v-card-text>
                <v-container>
                  <v-row>
                    <v-col cols="12" sm="6" md="4">
                      <v-text-field
                        v-model="editedItem.name"
                        label="П.І.П"
                      ></v-text-field>
                    </v-col>
                    <v-col cols="12" sm="6" md="4">
                      <v-text-field
                        v-model="editedItem.dateBirth"
                        label="Дата народження"
                      ></v-text-field>
                    </v-col>
                    <v-col cols="12" sm="6" md="4">
                      <v-text-field
                        v-model="editedItem.phoneNumber"
                        label="Номер телефону"
                      ></v-text-field>
                    </v-col>
                    <v-col cols="12" sm="6" md="4">
                      <v-text-field
                        v-model="editedItem.email"
                        label="Email"
                      ></v-text-field>
                    </v-col>
                  </v-row>
                </v-container>
              </v-card-text>

              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="blue darken-1" text @click="close">
                  Cancel
                </v-btn>
                <v-btn color="blue darken-1" text @click="save"> Save </v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>
          <v-dialog v-model="dialogDelete" max-width="500px">
            <v-card>
              <v-card-title class="text-h5"
                >Ви впевнені, що хочете видалити цей елемент?</v-card-title
              >
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="blue darken-1" text @click="closeDelete"
                  >Cancel</v-btn
                >
                <v-btn color="blue darken-1" text @click="deleteItemConfirm"
                  >OK</v-btn
                >
                <v-spacer></v-spacer>
              </v-card-actions>
            </v-card>
          </v-dialog>
        </v-toolbar>
      </template>
      <template v-slot:item.actions="{ item }">
        <v-icon small class="mr-2" @click="editItem(item)"> mdi-pencil </v-icon>
        <v-icon small @click="deleteItem(item)"> mdi-delete </v-icon>
      </template>
      <template v-slot:no-data>
        <v-btn color="primary" @click="initialize"> Reset </v-btn>
      </template>
    </v-data-table>
  </div>
</template>


<script>
export default {
  data: () => ({
    dialog: false,
    dialogDelete: false,
    search: "",
    headers: [
      {
        text: "П.І.П.",
        align: "start",
        value: "name",
      },
      { text: "Дата народження", value: "dateBirth" },
      { text: "Номер телефону", value: "phoneNumber" },
      { text: "Email", value: "email" },
      { text: "Actions", value: "actions", sortable: false },
    ],
    items: [],
    editedIndex: -1,
    editedItem: {
      name: "",
      dateBirth: "",
      phoneNumber: "",
      email: "",
    },
    defaultItem: {
      name: "",
      dateBirth: "",
      phoneNumber: "",
      email: "",
    },
  }),

  computed: {
    formTitle() {
      return this.editedIndex === -1 ? "Створити новий запис" : "Редагування";
    },
  },

  watch: {
    dialog(val) {
      val || this.close();
    },
    dialogDelete(val) {
      val || this.closeDelete();
    },
  },

  created() {
    this.initialize();
  },

  methods: {
    initialize() {
      this.items = [
        {
          name: "Пантюшко Ілля Русланович",
          dateBirth: "31.07.2001",
          phoneNumber: "0960308146",
          email: "illia.pantiushko@oa.edu.ua",
        },
        {
          name: "Бунтін Максим Анатолійович",
          dateBirth: "01.12.2001",
          phoneNumber: "0930308134",
          email: "maksym.buntin@oa.edu.ua",
        },
        {
          name: "Грищук Микола Володимирович",
          dateBirth: "21.03.2001",
          phoneNumber: "0970308345",
          email: "mykola.hryshchuk@oa.edu.ua",
        },
        {
          name: "Ковбасюк Олександр Михайлович",
          dateBirth: "11.10.2001",
          phoneNumber: "0980308342",
          email: "oleksandr.kovbasiuk@oa.edu.ua",
        },
        {
          name: "Коваль Ростислав Васильович",
          dateBirth: "25.08.2001",
          phoneNumber: "0960308146",
          email: "rostyslav.koval@oa.edu.ua",
        },
        {
          name: "Неручок Богдан Русланович",
          dateBirth: "18.06.2001",
          phoneNumber: "0960308146",
          email: "bohdan.neruchok@oa.edu.ua",
        },
        {
          name: "Садовник Денис Ішорович",
          dateBirth: "27.05.2001",
          phoneNumber: "0970303142",
          email: "denys.sadovnyk@oa.edu.ua",
        },
        {
          name: "Цезарук Софія Юрівна",
          dateBirth: "10.09.2001",
          phoneNumber: "0696362819",
          email: "sofiia.tsezaruk@oa.edu.ua",
        },
        {
          name: "Мороз Олександр Миколаєвич",
          dateBirth: "14.05.2001",
          phoneNumber: "0342295272",
          email: "olexandr.moroz@oa.edu.ua",
        },
        {
          name: "Демидюк Михайло Дмитрович",
          dateBirth: "12.12.2001",
          phoneNumber: "0527258572",
          email: "mykhailo.demydiuk@oa.edu.ua",
        },
      ];
    },

    editItem(item) {
      this.editedIndex = this.items.indexOf(item);
      this.editedItem = Object.assign({}, item);
      this.dialog = true;
    },

    deleteItem(item) {
      this.editedIndex = this.items.indexOf(item);
      this.editedItem = Object.assign({}, item);
      this.dialogDelete = true;
    },

    deleteItemConfirm() {
      this.items.splice(this.editedIndex, 1);
      this.closeDelete();
    },

    close() {
      this.dialog = false;
      this.$nextTick(() => {
        this.editedItem = Object.assign({}, this.defaultItem);
        this.editedIndex = -1;
      });
    },

    closeDelete() {
      this.dialogDelete = false;
      this.$nextTick(() => {
        this.editedItem = Object.assign({}, this.defaultItem);
        this.editedIndex = -1;
      });
    },

    save() {
      if (this.editedIndex > -1) {
        Object.assign(this.items[this.editedIndex], this.editedItem);
      } else {
        this.items.push(this.editedItem);
      }
      this.close();
    },
  },
};
</script>