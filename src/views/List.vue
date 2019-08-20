<template>
  <div>
    <v-form>
      <v-container>
        <v-row>
          <v-col cols="12" sm="4">
            <v-text-field
              label="title"
              v-model="newItem.title"
              @keypress.enter="addItem"
            ></v-text-field>
          </v-col>
          <v-col cols="12" sm="4">
            <v-text-field
              label="content"
              v-model="newItem.content"
              @keypress.enter="addItem"
            ></v-text-field>
          </v-col>
          <v-col cols="12" sm="4">
            <v-btn
              block
              color="success"
              @click="addItem"
              :disabled="
                newItem.content.length == 0 || newItem.title.length == 0
              "
              >Add
            </v-btn>
          </v-col>
        </v-row>
      </v-container>
    </v-form>

    <v-expansion-panels>
      <v-expansion-panel v-for="(item, i) in listArray" :key="i">
        <v-expansion-panel-header :class="item.completed ? 'success' : ''">
          {{ item.title }}
        </v-expansion-panel-header>
        <v-expansion-panel-content>
          <v-card flat>
            <v-card-text>
              {{ item.content }}
            </v-card-text>
            <v-divider />
            <v-card-actions>
              <v-spacer />
              <v-btn
                color="info"
                right
                @click="item.completed = !item.completed"
                >Toggle Completed</v-btn
              >
            </v-card-actions>
          </v-card>
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-expansion-panels>
  </div>
</template>

<script>
export default {
  name: "List",
  methods: {
    addItem() {
      if (this.newItem.content.length == 0 || this.newItem.title.length == 0)
        return;
      this.listArray.push({ ...this.newItem });
      this.newItem = { title: "", content: "", completed: false };
    }
  },
  data() {
    return {
      newItem: { title: "", content: "", completed: false },
      listArray: [
        { title: "this is a title", content: "aaaaa", completed: true },
        { title: "this is a title", content: "aaaaa", completed: false },
        { title: "this is a title", content: "aaaaa", completed: false },
        { title: "this is a title", content: "aaaaa", completed: false },
        { title: "this is a title", content: "aaaaa", completed: false }
      ]
    };
  }
};
</script>

<style scoped></style>
