<template>

  <aside class="sidebar">

    <div class="logo">
      LOGO
    </div>

    <nav class="menu">

      <a href="#" class="menu-item active">
        Categories
      </a>

      <a href="#" class="menu-item">
        Widgets
      </a>

      <a href="#" class="menu-item">
        ...
      </a>

    </nav>

  </aside>

</template>

<style scoped>

.sidebar {
  width: 240px;
  min-width: 240px;
  height: 100vh;

  flex-shrink: 0;

  background: white;
  border-right: 1px solid #e5e7eb;

  padding: 20px;
}

.logo {
  font-size: 22px;
  font-weight: bold;

  margin-bottom: 30px;
}

.menu {
  display: flex;
  flex-direction: column;

  gap: 8px;
}

.menu-item {
  display: block;

  padding: 12px 15px;

  text-decoration: none;
  color: #555;

  border-radius: 8px;
}

.menu-item:hover {
  background: #f3f4f6;
}

.menu-item.active {
  background: #e8f0ff;
  color: #2563eb;

  font-weight: 600;
}

</style>