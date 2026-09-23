<script setup>
import Sidebar from './components/Sidebar.vue'
import Header from './components/Header.vue'
import Categories from './components/Categories/Categories.vue'
</script>

<template>
  <div class="layout">

    <Sidebar />

    <div class="main-content">
      <Header />
      <Categories />
    </div>

  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body,
#app {
  width: 100%;
  min-width: 100%;
  min-height: 100vh;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, sans-serif;
  background: #f5f6fa;
}

.layout {
  display: flex;

  width: 100%;
  min-width: 100%;
  min-height: 100vh;

  margin: 0;
  padding: 0;
}

.main-content {
  flex: 1;
  min-width: 0;
  width: auto;

  margin: 0;
  padding: 0;
}
</style>