<script setup lang="ts">

import { ref } from "vue";
import { storeToRefs } from "pinia";
import { useCounterStore } from "../store/counter";
import { defineProps } from "vue";
defineProps<{ msg: string }>();

const { count } = storeToRefs(useCounterStore());
const filePath = ref(null);
const openFile = async () => {
  //@ts-ignore
  filePath.value = await window.electronAPI.openFile();
};
</script>
<template>
  <div style="background-color: beige">
    <h1>Home Page</h1>
    <img :src="imageUrl" alt="home logo" width="100" height="100" />
    <h1>Home Page</h1>
    <img :src="imageUrl" alt="home logo" width="100" height="100" />
  </div>

</template>