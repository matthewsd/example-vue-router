<template>
  <v-expansion-panels>
    <v-expansion-panel v-for="(item, i) in listArray" :key="i">
      <v-expansion-panel-header>{{ item.title }}</v-expansion-panel-header>
      <v-expansion-panel-content>
        {{ item.content }}
      </v-expansion-panel-content>
    </v-expansion-panel>
  </v-expansion-panels>
</template>

<script>
export default {
  name: "List",
  data() {
    return {
      listArray: [
        { title: "this is a title", content: "aaaaa" },
        { title: "this is a title", content: "aaaaa" },
        { title: "this is a title", content: "aaaaa" },
        { title: "this is a title", content: "aaaaa" },
        { title: "this is a title", content: "aaaaa" }
      ]
    };
  }
};
</script>

<style scoped></style>
