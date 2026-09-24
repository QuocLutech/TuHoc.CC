<script setup>

defineProps({

  id: Number,

  name: String,

  productCount: Number,

  status: String

})

</script>


<template>

  <div class="category-card">

    <!-- Phần trên -->

    <div class="card-top">

      <!-- ID -->

      <div class="category-id">

        {{ String(id).padStart(2, '0') }}

      </div>


      <!-- Nút 3 chấm -->

      <button class="more-btn">

        ⋮

      </button>

    </div>


    <!-- Thông tin Category -->

    <div class="category-info">

      <h3>

        {{ name }}

      </h3>

      <p>

        WIDGET · {{ productCount }} items

      </p>

    </div>


    <!-- Phần dưới -->

    <div class="card-bottom">

      <span class="status">

        ✓ {{ status }}

      </span>


      <button class="edit-btn">

        ✎

      </button>

    </div>

  </div>

</template>


<style scoped>

.category-card {

  width: 100%;
  /* width: 100% → card rộng bằng phần tử cha */

  background: #ffffff;

  border: 1px solid #e5e7eb;
  /* border → tạo đường viền */

  border-radius: 12px;
  /* border-radius → bo tròn góc */

  padding: 20px;
  /* padding → khoảng cách từ nội dung đến viền */

  box-sizing: border-box;
  /* box-sizing → giúp padding không làm card vượt quá kích thước */

  transition: all 0.2s ease;
  /* transition → hiệu ứng thay đổi mượt */

}


.category-card:hover {

  border-color: #d1d5db;

  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.06);
  /* box-shadow → tạo bóng xung quanh card */

}

.card-top {

  display: flex;
  /* flex → đưa ID và nút 3 chấm lên cùng một hàng */

  align-items: center;
  /* Căn giữa theo chiều dọc */

  justify-content: space-between;
  /* ID bên trái, nút 3 chấm bên phải */

}

.category-id {

  width: 34px;

  height: 34px;

  display: flex;

  align-items: center;

  justify-content: center;

  background: #2563eb;

  color: white;

  border-radius: 8px;

  font-size: 14px;

  font-weight: 600;

}

.more-btn {

  width: 32px;

  height: 32px;

  display: flex;

  align-items: center;

  justify-content: center;

  border: none;

  border-radius: 6px;

  background: transparent;

  color: #6b7280;

  font-size: 20px;

  cursor: pointer;

  transition: background 0.2s;

}

.more-btn:hover {

  background: #f3f4f6;

}

.category-info {

  margin-top: 16px;

}

.category-info h3 {

  margin: 0;

  font-size: 16px;

  font-weight: 600;

  color: #1f2937;

}


.category-info p {

  margin: 6px 0 0;

  font-size: 12px;

  color: #94a3b8;

}

.card-bottom {

  margin-top: 20px;

  padding-top: 15px;

  border-top: 1px solid #f0f0f0;

  display: flex;

  align-items: center;

  justify-content: space-between;

}

.status {

  display: inline-block;

  padding: 5px 10px;

  border-radius: 6px;

  background: #ecfdf3;

  color: #16a34a;

  font-size: 12px;

  font-weight: 500;

}

.edit-btn {

  border: none;

  background: transparent;

  color: #94a3b8;

  font-size: 18px;

  cursor: pointer;

}


.edit-btn:hover {

  color: #2563eb;

}

</style>