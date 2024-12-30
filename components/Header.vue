<template>
  <header class="bg-gray-800 text-white py-4">
    <Menubar :model="menuItems" class="container mx-auto" />
  </header>
</template>

<script setup>
const menuItems = [
  { label: 'トップ', command: () => document.getElementById('top').scrollIntoView() },
  { label: '自己紹介', command: () => document.getElementById('about').scrollIntoView() },
  { label: 'スキル', command: () => document.getElementById('skill').scrollIntoView() },
  { label: 'コンテンツ', command: () => document.getElementById('content').scrollIntoView() },
];
</script>

<style scoped>
header {
  font-family: 'Inter', sans-serif;
}
</style>