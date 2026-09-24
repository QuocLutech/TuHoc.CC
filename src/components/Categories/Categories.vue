<script setup>
import {ref} from 'vue'
import CategoriesCard from './CategoriesCard.vue'
import CategoryModal from './CategoryModal.vue';

function handleAddCategory(category){
    const maxId = Math.max(
    ...categories.value.map(item => item.id))
    const newId = maxId + 1
  categories.value.push({
    id: newId,
    name: category.name,
    productCount : category.productCount,
    status: category.status
  })

  showModal.value = false
}

const showModal =ref(false)

const categories = ref([
  {
    id: 1,
    name: 'Electronic',
    productCount: 24,
    status: 'published'

  },
  {
    id: 2,
    name: 'Clothing',
    productCount: 19,
    status: 'Draft'
  },
  {
    id: 3,
    name: 'Books',
    productCount: 22,
    status: 'published'
  },
  {
    id: 4,
    name:'furniture',
    productCount: 15 ,
    status: 'Draft'
  }
])

</script>

<template>

  

  <main class="categories">

    <div class="page-header">

      <div>
        <h2>Categories</h2>

        <p>
          Manage your categories
        </p>
      </div>

      <button class="add-btn" @click="showModal = true">
        + Add Category
      </button>

    </div>

    <div class="categories-content">

      <CategoriesCard v-for="category in categories"
    :key="category.id"
    :name="category.name"
    :id="category.id"
    :status="category.status" 
    :productCount="category.productCount"

    />

    </div>

    <CategoryModal v-if="showModal" @add-category="handleAddCategory"   @close="showModal= false"/>

  </main>

</template>

<style scoped>
.categories {
  width: 100%;
  min-height: calc(100vh - 70px);
  padding: 30px;
  background: #f8f9fb;
}

/* Phần tiêu đề */
.page-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 30px;
}

.page-header h2 {
  margin: 0;
  font-size: 26px;
  font-weight: 600;
  color: #1f2937;
}

.page-header p {
  margin-top: 6px;
  font-size: 14px;
  color: #6b7280;
}

/* Nút Add Category */
.add-btn {
  border: none;
  background: #2563eb;
  color: white;

  padding: 11px 18px;

  border-radius: 8px;

  font-size: 14px;
  font-weight: 500;

  cursor: pointer;          /*con trỏ chuột */

  transition: 0.2s;
}

.add-btn:hover {
  background: #1d4ed8;
}

/* Danh sách card */
.categories-content {
  display: grid;

  grid-template-columns: repeat(3, minmax(0, 1fr));         /* tạo 3 cột , mỗi cột chia đều phần không gian còn lại ,cho phép co lại khi màn hình nhỏ */

  gap: 20px; /* khoảng cách giữa các category */
}


@media (max-width: 1000px) {
  .categories-content {
    grid-template-columns: repeat(2, minmax(0, 1fr)); /* Màn nhỏ hơn 1000px thì chia làm 2 cột */
  }
}


@media (max-width: 650px) {
  .categories {
    padding: 20px;
  }

  .page-header {
    align-items: flex-start;
    gap: 20px;
    flex-direction: column;
  }

  .categories-content {
    grid-template-columns: 1fr;
  }
}
</style>