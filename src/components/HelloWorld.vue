<script setup lang="ts">

import { ref } from "vue";
import { storeToRefs } from "pinia";
import { useCounterStore } from "../store/counter";
import { defineProps, defineSlots, defineModel, defineOptions } from "vue";
defineProps<{ msg: string }>();

const { count } = storeToRefs(useCounterStore());
const filePath = ref(null);
const openFile = async () => {
  //@ts-ignore
  filePath.value = await window.electronAPI.openFile();
};


