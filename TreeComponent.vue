<script setup lang="ts">
import TreeComponent from './TreeComponent.vue';

interface TreeData {
  key: string;
  title: string;
  children: TreeData[];
}
defineProps<{ data: TreeData[] }>();
</script>

<template>
  <!-- do something.... -->
  <div v-for="item in data" :key="item.key">
    <header>{{ item.title }}</header>

    <section v-if="item.children">
      <TreeComponent :data="item.children" />
    </section>
  </div>
</template>
