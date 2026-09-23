<template>

  <header class="header">

    <div class="header-left">
      <h1>Categories</h1>
    </div>

    <div class="header-right">

      <button class="icon-btn">
        🔔
      </button>

      <div class="user">
        User
      </div>

    </div>

  </header>

</template>

<style scoped>

.header {
  width: 100%;
  height: 70px;

  background: white;

  border-bottom: 1px solid #e5e7eb;

  display: flex;
  align-items: center;
  justify-content: space-between;

  padding: 0 30px;
}

.header-left h1 {
  font-size: 22px;
}

.header-right {
  display: flex;
  align-items: center;
  gap: 15px;
}

.icon-btn {
  border: none;
  background: transparent;

  font-size: 20px;
  cursor: pointer;
}

.user {
  padding: 8px 12px;

  background: #f3f4f6;

  border-radius: 8px;
}

</style>