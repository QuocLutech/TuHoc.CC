<script setup>
defineProps({
  name: String,              
  productCount: Number ,      //props : nhận tên , số lượng từ cha 
  status: String
})
</script>

<template>
  <div class="category-card">

   
    <div class="card-top">

   
      <div class="category-info">

        <div class="category-icon">
          📁
        </div>

        <div>
          <h3>
            {{ name }}
          </h3>

          <p>
            {{ productCount }} Products
          </p>
        </div>

      </div>


      <button class="more-btn">
        ⋮
      </button>

    </div>

  
    <div class="card-bottom">

      <span class="status">
        {{ status }}
      </span>

    </div>

  </div>
</template>

<style scoped>

.category-card {
  width: 100%;                       /* Độ rộng bằng 100% phần tử cha */

  background: #ffffff;             

  border: 1px solid #e5e7eb;         /* Viền: 1px, kiểu liền */

  border-radius: 12px;               /* Bo tròn 4 góc 12px */

  padding: 20px;                     /* Khoảng cách từ nội dung đến viền */

  transition: all 0.2s ease;        /* Tạo hiệu ứng chuyển động mượt */
}

.category-card:hover {
  border-color: #d1d5db;          

  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.06);
  /* Tạo bóng xung quanh card */
}

.card-top {
  display: flex;                     /* Sử dụng Flexbox */

  align-items: flex-start;           /* Căn các phần tử theo chiều dọc ở phía trên */

  justify-content: space-between;    /* Đẩy 2 phần tử về 2 phía */
}

.category-info {
  display: flex;                     /* Đặt icon và thông tin nằm cùng một hàng */

  align-items: center;               /* Căn giữa icon và nội dung theo chiều dọc */

  gap: 12px;                         /* Khoảng cách giữa icon và phần thông tin */
}


/* Icon */

.category-icon {
  width: 45px;               

  height: 45px;     

  display: flex;                    /* Sử dụng Flexbox */

  align-items: center;        

  justify-content: center;          

  flex-shrink: 0;                   /* Không cho icon bị co nhỏ lại */

  background: #eef4ff;              

  border-radius: 10px;               /* Bo tròn góc */

  font-size: 20px;                   /* Kích thước emoji/icon */
}

.category-info h3 {
  margin: 0 0 5px;                  /* Xóa margin mặc định, tạo khoảng cách dưới 5px */

  font-size: 16px;                 

  font-weight: 600;                  /* Độ đậm của chữ */

  color: #1f2937;                
}

.category-info p {
  margin: 0;                  

  font-size: 14px;                 

  color: #6b7280;               
}

.more-btn {
  width: 32px;                      

  height: 32px;                    

  display: flex;       

  align-items: center;            

  justify-content: center;           

  border: none;                      /* Không hiển thị đường viền */

  border-radius: 6px;               

  background: transparent;           /* Nền trong suốt */

  color: #6b7280;                  

  font-size: 20px;                

  cursor: pointer;                   /* Đổi con trỏ thành hình bàn tay */

  transition: background 0.2s;       /* Hiệu ứng đổi màu nền mượt */
}

.more-btn:hover {
  background: #f3f4f6;            
}


.card-bottom {
  margin-top: 20px;                 

  padding-top: 15px;                

  border-top: 1px solid #f0f0f0;    
}


.status {
  display: inline-block;             /* Cho phép áp dụng width/padding nhưng vẫn nằm cùng dòng */

  padding: 5px 10px;              

  border-radius: 20px;               

  background: #ecfdf3;               

  color: #16a34a;              

  font-size: 12px;                  

  font-weight: 500;              
}

</style>