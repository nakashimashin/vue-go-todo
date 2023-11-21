<script setup>
import { ref, computed } from 'vue';

const items = ref([
  { id: 1, name: 'aaaa' },
  { id: 2, name: 'bbbb' },
  { id: 3, name: 'ううう' },
]);

const sortOrder = ref(true);

const sortedItems = computed(() => {
  return [...items.value].sort((a, b) => {
    if (sortOrder.value) {
      return a.name.localeCompare(b.name);
    } else {
      return b.name.localeCompare(a.name);
    }
  });
});

const toggleSortOrder = () => {
  sortOrder.value = !sortOrder.value ;
  console.log(sortOrder);
  console.log(sortOrder.value);
}
</script>

<template>
  <div>
    <button @click="toggleSortOrder">並び替え</button>
    <div v-for="item in sortedItems" :key="item.id">
      <p>名前：{{ item.name }}さん</p>
      <p>会員番号：{{ item.id }}番</p>
      <p>##########</p>
    </div>
  </div>
</template>