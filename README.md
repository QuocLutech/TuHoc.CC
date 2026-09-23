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
		-Vue được xây dựng dựa trên HTML,CSS và JavaScript tiêu chuẩn .
		-Được tạo ra để đơn giản hóa việc phát triển ứng dụng bằng việc tái sử dụng các component(thành phần) và kiến trúc linh hoạt 
		
		
	#2.2 : Cách tạo project Vue : 
		 -npm create vue@latest ---> projecname ---> choose option ---> cd [projectname] --> npm install --> npm run dev 
		
	#2.3 : Cấu trúc Project Vue :
	
		1) src/ : Chứa mã nguồn
		
		2) App.vue : Đây là component(thành phần) chính trong dự án .
			- Một file .vue thường có 3 phần : <script setup>
											// JavaScript - Xử lý logic
											   </script>
											   <template>
  											   <!-- HTML-Giao diện -->
											   </template>
											   <style>
											    /* CSS-Giao diện */
											   </style>
			 - App.vue còn được gọi là component cha .
											   
		3) main.js:Kết nối vue với HTML , Có nhiệm vụ import component chính của dự án đến thẻ id="app" trong file Index.html
		
		4) component/ : đây là nơi chứa các component nhỏ .
		
		5) assets/ : chứa tài nguyên của project : image/ , logo.png,style.css ,...
		
		6) public/: Chứa các file tĩnh
		
		7) package.json: chứa các thư viện project sử dụng.
		
		8) node_modules/ : chứa các thư viện đã cài
		
		9) Index.html : HTML

	#2.4 : component là gì : Là một khối giao diện (UI) , có thể tái sử dụng , bao gồm : HTML , CSS , JavaScript .
	
		1) Một component cần được " đăng kí " (toàn cục hoặc cục bộ )  để Vue biết được vị trí cài đặt của nó khi gặp trong template .
		- Đăng kí cục bộ : ví dụ tại App.vue : import [fileName] from './components/[fileName].vue' ==> chỉ được sử dụng ở App.vue còn ở file .vue 		khác sẽ không hiểu được mà không import .
		- Đăng kí toàn cục : import trong main.js 
		2) Cấu trúc : +Props: Dùng để truyền dữ liệu từ component cha xuống component con 
					  +Events($emit): Dùng để component con thông báo sự kiện hoặc truyền dữ liệu ngược lên component cha.
					  +Đăng ký (Registration): Có thể đăng ký dạng toàn cục (global) để dùng ở mọi nơi hoặc cục bộ (local) chỉ dùng trong một component khác.
	#2.5 : template : Giao diện dùng để định nghĩa câu trúc HTML của một component 
			- Các cú pháp :
				+ Interpolation(cú pháp nội suy) :Sử dụng cặp dấu ngoặc nhọn {{ }} để hiển thị dữ liệu dạng văn bản (text) hoặc thực hiện các biểu thức JavaScript đơn giản :Ví dụ: {{ message }} , {{ a*b * 2 }} , {{isOn?'On':'Off'}};
				
				+ Directives(chỉ thị của vue) : Là các thuộc tính  v-(tiền tố : Prefix) được gắn vào thẻ HTML để thực hiện các chức năng logic nó báo cho vue biết đây là một chỉ thị đặc biệt .
					* v-bind: gắn dữ liệu vào HTML (src, href, class, disabled). Ví dụ: <img v-bind :src="imageUrl" /> có thể 
				      													 viết tắt thành <img :src="imageUrl" />
					* v-model: Liên kết dữ liệu 2 chiều (two-way binding), thường dùng cho các ô nhập liệu (input, select, textarea). Ví dụ: <input v-model="searchText" />
					* v-if, v-else-if, v-else: Hiển thị theo điều kiện. Ví dụ: <p v-if="isLoggedIn">Bạn đã đăng nhập</p>
					* v-for: Lặp dữ liệu.Ví dụ: <li v-for="item in items" :key="item.id">{{ item.name }}</li>
					* v-on (hoặc viết tắt là @): bắt sự kiện (click, submit, keyup...).Ví dụ: <button @click="count++">Tăng số</button>

	#2.6 : Script : viết JS logic của component
		
	#2.7 : Style : CSS giao diện 

	
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
			
	 		- v-else :		<div v-if="điều_kiện">
 								 Nội dung khi đúng
							</div>

							<div v-else>
  								 Nội dung khi sai
							</div>
			![Ảnh bài học](https://github.com/user-attachments/assets/580c64f1-b60f-409f-b55a-33f21b88d20c)

			- v-show : ẩn hiện phần tử dựa trên điều kiện :
			 ![Ảnh bài học](https://github.com/user-attachments/assets/1ec87d0c-d9fb-469c-b66a-c0b125b9b5b8)

			- v-for :
					+Lặp qua mảng: v-for="item in items" hoặc v-for="(item, index) in items" (với index là số thứ tự bắt đầu từ 0).
						![Ảnh bài học](https://github.com/user-attachments/assets/13a90806-2afc-4274-956c-d0b0d20e6d09)
						
					+Lặp qua đối tượng: v-for="(value, key, index) in object" (lần lượt lấy giá trị, tên khóa và chỉ mục).
						![Ảnh bài học](https://github.com/user-attachments/assets/72e31cf5-4390-4782-b59d-5dbc8806f980)

					+Lặp theo khoảng số: v-for="n in 10" (lặp từ 1 đến 10)
						![Ảnh bài học](https://github.com/user-attachments/assets/20bebfac-abb8-4da1-8735-aeabc6421e9a)

					 

			- v-on / @click : - Trong vue nếu muốn một phần tử thay đổi và tự động cập nhật nên dùng ref();	
							  - .prevent: Gọi event.preventDefault() để ngăn hành vi mặc định của thẻ (như thẻ <a> không bị chuyển trang).
							  - .once: Sự kiện click chỉ được kích hoạt đúng một lần duy nhất.
						![Ảnh bài học](https://github.com/user-attachments/assets/22ee3690-4a2e-4da7-884e-ccffe60b317d)

			- v-model : - Người dùng nhập dữ liệu ---> biến được cập nhật tự động. Nó dùng để liên kết dữ liệu với input.
						![Ảnh bài học](github.com/user-attachments/assets/a2303842-54be-4743-8fc9-1a059da03788)
						![Ảnh bài học](https://github.com/user-attachments/assets/cd975ee1-3de7-452a-ae89-b734b8fde0eb)


			
			- Event : -là một hành động xảy ra trên trang web do người dùng hoặc trình duyệt thực hiện.
					  -Ví dụ:  Click vào nút → click,Nhập dữ liệu → input,Gửi form → submit,Di chuyển chuột → mouseover,Nhấn phím → keydown
					  -Trong vue chúng ta thường dùng v-on hoặc kí hiệu @ để bắt even
						Gửi form → submit
						Click vào nút → click
						Nhập dữ liệu → input
						Gửi form → submit
						Di chuyển chuột → mouseover
						Nhấn phím → keydown
					   ![Ảnh bài học](https://github.com/user-attachments/assets/e3d5ead8-f748-415a-b539-999f427e0881)

			 - Class binding : là cách vue cho phép bạn thay đổi class của HTML dựa trên dữ liệu.
			 			![Ảnh bài học](https://github.com/user-attachments/assets/f6d41da9-198a-4108-a062-a51d4ed7d78c_
						
			 - Style binding : Cho phép thay đổi CSS dựa trên csdl.
			 			![Ảnh bài học]https://github.com/user-attachments/assets/59e433eb-dfb6-4dde-89a1-9c3763b9b7a7

						


##4 : Tạo component

	#4.1 : Tạo component 
		src/components/[tenFile].vue

	#4.2 : Import component
		- Trong file App.vue 
		ví dụ :
		<script setup>
			import [tenFile] from './components/[tenFile].vue'
		</script>
	
	#4.3 : Props
		-Là cách để imponent cha [App.vue] truyền dữ liệu xuống imponent con [src/imponents/[tenFileCon].vue]
		- ví dụ : 
				Component con : Product.vue 
					<script setup>
						defineProps(['name'])
					</script>
					<template> <h2> {{name}} </h2> </template>
					
				Component cha : App.vue 
					<script setup>
						import Product from './src/pronents/Product.vue'
					</script>
					<template>
						<Product name="Áo Thun" /> 
						<Product name="Quần" /> 
						<Product name="Mũ" /> 
					</template>
				//Ở ví dụ này name="tenSP" chính là props .
				
		-Có thể truyền nhiều props ![Ảnh bài học](https://github.com/user-attachments/assets/a8eb2115-0a32-44d0-8f59-291fb1225168).
		
		*** Truyền số , boolean , biến : 
			+ <Product price ="10000" /> thì price ở đây là chuỗi 
			+ <Product :price ="1000" /> thì price ở đây là số
			+ <Product :is-sale="true" /> boolean
			+Truyền biến : 	<script setup>
								const productPrice = 100000
							</script>

							<template>
  								<Product :price="productPrice" />
							</template>

		***Khai báo props bằng object : 
			- Thay vì khai báo :  definePops(['name','price']) 
			- Thì có thể 		<script setup>
									defineProps({
  									name: String,
 									price: Number
											})
								</script>

		***Props là dữ liệu một chiều , component con không nên trực tiếp thay đổi props , nếu cần thay đổi component con sẽ dùng Event để thông báo ngược lên component cha.

		

		
		
		
	
	#4.4 : Emit
		+Dùng để báo sự kiện từ component con lên cha
		+Ví dụ : con có nút mua hàng , khi ấn vào sẽ báo sự kiện lên để cha xử lý thông tin 
			ProductCard.vue --	<button @click="emit('muaHang')">
     							 	Mua hàng
    							</button>
			Thì App.vue bắt sự kiện như sau :  <ProductCard name="Áo" :price="10000" @muaHang="xuLyMuaHang"/> và cần 1 function xử lý sự kiện : function xuLyMuaHang(){alert('Bạn đã mua sản phẩm')}
		
		

	
	#4.5 : Component communication
	
		+ Đây là cách các component con trao đổi dữ liệu và sự kiện với nhau .
		+ Không nên truyền trực tiếp mà thường thông qua component cha .  [con1].vue ---> App.vue ---> [con2].vue  . Hoặc khi ứng dụng lớn, có thể dùng state management như Pinia.
		+ Vue có cách để truyền dữ liệu sâu xuống nhiều component con bằng provide/inject 
	
	- Giả sử   https://github.com/user-attachments/assets/c13fb76c-e137-495f-8e0c-30ef3a309a2f
	***Ở ảnh này có thể thấy : + App.vue chứa ProductList : 	<script setup>
																	import ProductList from './components/ProductList.vue'
																</script
							   + ProductList lại chứa lại chứa ProductCard : 	<script setup>
																					import ProductCard from './ProductCard.vue'
																				</script>	
							   + Tương tự ProductCard lại chưa BuyButton .
							   + BuyButton.vue : <template> <button>Mua hàng </Button> </template>
							   + Các component con đang lồng nhau nhiều lớp và nếu App.vue cò thông tin const userName= 'Quốc' và BuyButton cần biest thông tin khi nó nằm ở 3 lớp bên dưới nếu chỉ sử dụng Pops thì tức là
							   		ProducList và ProductCard ko cần đến thông tin này nhưng vẫn phải nhận rồi truyền tiếp ==> khi đó ta sử dụng provide/inject hữu ích .
							   + Thay vì App --props--> ProductList --props--> ProductCard --props--> BuyButton thì App --provide--> ProductList --> ProductCard --> BuyButton <--inject--
									
		
	#4.4 : Slot
		-để component cha truyền 1 đoạn HTML team play vago vị trí mà component con chỉ định //props truyền dữ liệu thì slot truyền nội dung giao 	diện.
	
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






	
	
		
					
		
		




