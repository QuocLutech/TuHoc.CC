<script setup>

import { ref } from 'vue'

const name = ref('')
const productCount = ref(0)

const status = ref('Draft')

const emit = defineEmits(['add-category','close'])  // gửi 2 sự kiện lên cha , add thêm category hoặc thoát

defineProps({
  id: Number,
  name: String,
  productCount: Number,
  status: String
})

function addCategory(){
  const category= {
    name:name.value,
    productCount:Number(productCount.value),
    status: status.value
  }
  emit('add-category',category)
}
</script>

<template>

  <div class="modal-overlay">

    <div class="modal">

      <h2>Add Category</h2>

      <div class="form-group">
        <label>Name</label>
        <input
          v-model="name"
          type="text"
          placeholder="Enter category name"
        >
      </div>

      <div class="form-group">
        <label>Product Count</label>
        <input
          v-model="productCount"
          type="number"
          min="0"
        >
      </div>

      <div class="form-group">
        <label>Status</label>

        <select v-model="status">
          <option value="Published">Published</option>
          <option value="Draft">Draft</option>
        </select>

      </div>

      <div class="modal-actions">

        <button class="cancel-btn" @click="emit('close')">
          Cancel
        </button>

        <button class="add-btn" @click="addCategory">
          Add
        </button>

      </div>

    </div>

  </div>

</template>

<style scoped>

.modal-overlay {
  position: fixed;
  inset: 0;

  background: rgba(0, 0, 0, 0.4);

  display: flex;
  align-items: center;
  justify-content: center;
}

.modal {
  width: 400px;

  background: white;

  padding: 25px;

  border-radius: 12px;
}

.modal h2 {
  margin-top: 0;
  margin-bottom: 20px;
}

.form-group {
  margin-bottom: 15px;
}

.form-group label {
  display: block;
  margin-bottom: 6px;

  font-size: 14px;
  font-weight: 500;
}

.form-group input,
.form-group select {
  width: 100%;

  padding: 10px;

  border: 1px solid #d1d5db;
  border-radius: 6px;

  box-sizing: border-box;
}

.modal-actions {
  display: flex;
  justify-content: flex-end;

  gap: 10px;

  margin-top: 20px;
}

.cancel-btn,
.add-btn {
  padding: 10px 16px;

  border: none;
  border-radius: 6px;

  cursor: pointer;
}

.cancel-btn {
  background: #e5e7eb;
}

.add-btn {
  background: #2563eb;
  color: white;
}

</style>