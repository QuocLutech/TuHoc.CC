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
- [ ] DOM : là cách JS điều khiển Html.
- [ ] Event
- [ ] LocalStorage
- [ ] JSON

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
		
	
	#2.7 : Style : CSS giao diện 
	
	#2.8 : Cách sử dụng Vue DevTools : sử dụng Vue DevTools để theo dõi được sự thay đổi của dữ liệu , event , Vuex.
	
##3 : Vue cơ bản 

	#3.1 : Interpolation(Nội suy ) : Đưa dữ liệu từ JS vào HTML
		*Ví dụ trong App.vue  : 
		<script setup>
		const name = "Quốc";
		</script>

		<template>
		<h1>Xin chào {{ name }}</h1>
		</template>

		*Vue sẽ lấy name="Quốc" để đưa vào {{name}} 
		*Hiển thị được nhiều biến.
		*Thực hiện được các phép tính:  <script setup> const a = 10; const b=11; </script>
										<template> <p> Tổng {{a}} + {{b}} = {{a+b}}  </p> </template>
		
		
	
	
	#3.2 :  Binding dữ liệu : Kết nối dữ liệu trong JavaScript với giao diện HTML, để khi dữ liệu thay đổi thì giao diện có thể thay đổi theo. Trong Vue một trong những cách quan trọng nhất là v-bind
			- v-bind : <script setup>
							const imageUrl = "https://example.com/cat.jpg";
						</script>

						<template>
						    <img v-bind:src="imageUrl">
						</template>
			-Vue sẽ hiểu : v-bind: src="imageUrl"----> lấy giá trị imageUrl ----> Gán vào thuộc tính src
			-Thay vì <img v-bind:src="imageUrl"> thì có thể viết <img :src="imageUrl"> (img , href, class , id )
			![Ảnh bài học](https://github.com/user-attachments/assets/21e85227-4be8-4213-b7bb-67c8f5d901ff)

			- v-if : sử dụng để hiển thị khối lệnh có điều kiện . ĐK đúng thì hiển thị còn sai thì ko .
			![Ảnh bài học](https://github.com/user-attachments/assets/1108b330-37b7-4634-9299-3fcf4ce4219e)

			
			
	- [ ] v-else
	- [ ] v-show
	- [ ] v-for
	- [ ] v-on / @click
	- [ ] v-model
	- [ ] Event
	- [ ] Class binding
	- [ ] Style binding

##4 : Tạo component

	- [ ] Tạo component
	- [ ] Import component
	- [ ] Props
	- [ ] Emit
	- [ ] Component communication
	- [ ] Slot
	- [ ] Component tái sử dụng

##5 : Reactivity

	- [ ] ref()
	- [ ] reactive()
	- [ ] computed()
	- [ ] watch()
	- [ ] Hiểu cơ chế Reactive của Vue

##6 : Lifecycle & Composition API

	- [ ] onMounted()
	- [ ] onUpdated()
	- [ ] onUnmounted()
	- [ ] Composition API
	- [ ] Script Setup
	- [ ] Tạo composable

##7 : Làm việc với API

 	- [ ] Fetch API
	- [ ] Axios
	- [ ] GET
	- [ ] POST
	- [ ] PUT
	- [ ] DELETE
	- [ ] Loading
	- [ ] Error handling
	- [ ] Hiển thị dữ liệu API lên Vue.

##8 : Vue Router

##9 : State Management






	
	
		
					
		
		




