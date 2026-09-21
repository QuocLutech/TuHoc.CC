//🎯MỤC TIÊU🎯 : Vue.js từ cơ bản đến có thể tự xây dựng một website thực tế.

##1:Chuẩn bị kiến thức JavaScript.

- [ ] Biến: let, const, var
- [ ] Kiểu dữ liệu
- [ ] if / else
- [ ] for / while
- [ ] Function
- [ ] Arrow Function
- [ ] Array
- [ ] Object
- [ ] Destructuring
- [ ] Spread Operator
- [ ] map()
- [ ] filter()
- [ ] find()
- [ ] reduce()
- [ ] Promise
- [ ] async / await
- [ ] Fetch API
- [ ] ES6 Modules

##2:Vue

	#2.1 : Vue là gì ? 
		-Vue là một framework dùng để xây dựng giao diện người dùng (user interface) .
		-giúp chia một trang web lớn thành nhiều mảnh nhỏ có giao diện và logic riêng gọi là component(thành phần ) , những mảnh này có thể tái sử dụng (reuse). 
		
	#2.2 : Cách tạo project Vue : 
		+Bước 1: Đảm bảo cài đặt phiên bản node.js mới nhất 
		+Bước 2: Tạo cấu trúc dự án Vue : </> npm create vue@latest ---> projecname ---> choose option ---> cd [projectname] --> npm install --> npm run dev 
		
	#2.3 : Cấu trúc Project Vue :
	
		1) src/ : Code
		
		2) App.vue : Đây là component(thành phần) gốc của ứng dụng .
			- Ví dụ :  <template> <h1> hello world </h1> </template>
			- Một file .vue thường có 3 phần : <script setup>
											// JavaScript - Xử lý logic
											   </script>
											   <template>
  											   <!-- HTML-Giao diện -->
											   </template>
											   <style>
											    /* CSS-Giao diện */
											   </style>
											   
		3) main.js:
		
		4) component/ : đây là nơi chứa các component nhỏ .
		
		5) assets/ : chưa tài nguyên của project : image/ , logo.png,style.css ,...
		
		6) public/:
		
		7) package.json: chứa các thư viện project sử dụng.
		
		8) node_modules/ : chưa các thư viện đã cài
		
		9) Index.html : HTML

	#2.4 : component là gì : Là một khối giao diện (UI) , có thể tái sử dụng , bao gồm : HTML , CSS , JavaScript .
	
		1) Một component cần được " đăng kí " (toàn cục hoặc cục bộ )  để Vue biết được vị trí cài đặt của nó khi gặp trong template .
		2) Cấu trúc : +Props: Dùng để truyền dữ liệu từ component cha xuống component con 
					  +Events($emit): Dùng để component con thông báo sự kiện hoặc truyền dữ liệu ngược lên component cha.
					  +Đăng ký (Registration): Có thể đăng ký dạng toàn cục (global) để dùng ở mọi nơi hoặc cục bộ (local) chỉ dùng trong một component khác.
	#2.5 : template : Giao diện dùng để định nghĩa câu trúc HTML của một component 
			- Các cú pháp :
				+ Interpolation(cú pháp nội suy) :Sử dụng cặp dấu ngoặc nhọn {{ }} để hiển thị dữ liệu dạng văn bản (text) hoặc thực hiện các biểu thức JavaScript đơn giản :Ví dụ: {{ message }} , {{ a*b * 2 }} , {{isOn?'On':'Off'}};
				
				+ Directives(chỉ thị của vue) : Là các thuộc tính  v-(tiền tố : Prefix) được gắn vào thẻ HTML để thực hiện các chức năng logic nó báo cho vue biết đây là một chỉ thị đặc biệt .
					* v-bind: gắn dữ liệu vào HTML (ví dụ: src, href, class, disabled). Ví dụ: <img v-bind :src="imageUrl" />
					* v-model: Liên kết dữ liệu 2 chiều (two-way binding), thường dùng cho các ô nhập liệu (input, select, textarea). Ví dụ: <input v-model="searchText" />
					* v-if, v-else-if, v-else: Hiển thị theo điều kiện. Ví dụ: <p v-if="isLoggedIn">Bạn đã đăng nhập</p>
					* v-for: Lặp dữ liệu.Ví dụ: <li v-for="item in items" :key="item.id">{{ item.name }}</li>
					* v-on (hoặc viết tắt là @): bắt sự kiện (click, submit, keyup...).Ví dụ: <button @click="count++">Tăng số</button>

	#2.6 : Script : viết JS logic của component
		-
	
	#2.7 : Style
	
	#2.8 : Cách sử dụng Vue DevTools
	
	
		
					
		
		




