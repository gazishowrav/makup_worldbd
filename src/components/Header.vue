<template>
    <!-- header -->
	<header class="header">
		<!-- top header-->
		<div class="top-header">
			<div class="container-wrapper">
				<nav class="navbar navbar-expand-lg px-lg-0">
				  <a class="navbar-brand" href="#">
				  	<img :src="logo" alt="makeup-world-bd-logo">
				  </a>
				  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
				    <span class="navbar-toggler-icon"></span>
				  </button>

				  <div class="collapse navbar-collapse" id="navbarSupportedContent">
				    <ul class="navbar-nav m-auto">
				    	<li class="nav-item active">
					        <router-link class="nav-link" to="/">Home <span class="sr-only">(current)</span></router-link>
				      	</li>
				      <slot v-for="item in makeup">
				      	<slot v-if="item.position==0">
					      	<li class="nav-item dropdown">
					        	<a class="nav-link dropdown-toggle" href="#" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">{{item.name}}</a>
								<!--Dropdown-->
					        	<div class="dropdown-menu megamenu-lg" aria-labelledby="dropdownMenuButton">
						            <div class="row">
						            	<div class="col-lg-4" v-for="megamenu in item.megamenu" :key="megamenu">
	                          				<h4 class="menu-head">
	                          				    <router-link to="/">{{megamenu.name}}</router-link>
	                          				</h4>
	                          				<ul class="nav flex-column">
	                          					<li class="nav-item">
	                          						<a href="#" class="nav-link">{{megamenu.name}}</a>
	                          					</li>
	                          				</ul>
	                          			</div>
						            </div>
						        </div>
					        </li>
					    </slot>
					    <!-- <slot v-else>
					    	<li class="nav-item">
					    	  <router-link :to="/">{{item.name}}</router-link>
					    	</li>
					    </slot> -->
				      </slot>
				      <slot v-for="item in kachabazar">
				      	<slot v-if="item.position==0">
					      	<li class="nav-item dropdown">
					        	<a class="nav-link dropdown-toggle" href="#" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">{{item.name}}</a>
								<!--Dropdown-->
					        	<div class="dropdown-menu megamenu-lg" aria-labelledby="dropdownMenuButton">
						            <div class="row">
						            	<div class="col-lg-4" v-for="megamenu in item.megamenu" :key="megamenu">
	                          				<h4 class="menu-head">
	                          				    <router-link to="/">{{megamenu.name}}</router-link>
	                          				</h4>
	                          				<ul class="nav flex-column">
	                          					<li class="nav-item">
	                          						<a href="#" class="nav-link">{{megamenu.name}}</a>
	                          					</li>
	                          				</ul>
	                          			</div>
						            </div>
						        </div>
					        </li>
					    </slot>
					    <!-- <slot v-else>
					    	<li class="nav-item">
					    	  <router-link :to="/">{{item.name}}</router-link>
					    	</li>
					    </slot> -->
				      </slot>
				    </ul>
				  </div>
				</nav>
			</div>
		</div>
		<!-- /top header-->
		<!-- main header-->
		<div class="main-header">
			<div class="container-wrapper">
				<div class="row align-items-center">
					<div class="col-lg-3">
						<div class="btn-catagory" v-on:click="isActive = !isActive" v-bind:class="{ show: isActive }">
							<span class="btn btn-light shadow-none"><i class="mdi mdi-format-list-bulleted"></i></span>
							<p class="mb-0">Shop By <br>
							<span>Categories</span></p>
							<!-- Dropdown Menu -->
							<ul class="nav categories-dropdown">
							    <li class="nav-item">
							    	<a href="products.html" class="nav-link">Accessories</a>
							    </li>
							    <li class="nav-item">
							    	<a href="products.html" class="nav-link">Appliances</a>
							    </li>
							    <li class="nav-item">
							    	<a href="products.html" class="nav-link">Bags</a>
							    </li>
							    <li class="nav-item">
							    	<a href="products.html" class="nav-link">Camera</a>
							    </li>
							    <li class="nav-item">
							    	<a href="products.html" class="nav-link">Electronic</a>
							    </li>
							    <li class="nav-item">
							    	<a href="products.html" class="nav-link">Entertainment</a>
							    </li>
							    <li class="nav-item">
							    	<a href="products.html" class="nav-link">Induction</a>
							    </li>
							    <li class="nav-item">
							    	<a href="products.html" class="nav-link">Luggages</a>
							    </li>
							    <li class="nav-item">
							    	<a href="products.html" class="nav-link">Mobile Phone</a>
							    </li>
							    <li class="nav-item">
							    	<a href="products.html" class="nav-link">Packaging & Printing</a>
							    </li>
						  	</ul>
							<!-- /Dropdown Menu -->
						</div>
					</div>
					<div class="col-lg-5">
						<div class="search-box">
							<div class="input-group">
							  <div class="input-group-prepend dropdown">
							    <span class="input-group-text dropdown-toggle" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">All Catagories</span>
							    <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
							        <a class="dropdown-item" href="#">Entertainment</a>
							        <a class="dropdown-item" href="#">Electronic</a>
							        <a class="dropdown-item" href="#">Packaging & Printing</a>
							      </div>
							  </div>
							  <input type="text" class="form-control" placeholder="Search Products">
							  <div class="input-group-append">
							    <span class="input-group-text">
							    	<i class="mdi mdi-magnify"></i>
							    </span>
							  </div>
							</div>
						</div>
					</div>
					<div class="col-lg-4 text-right">
						<div class="cart-box d-flex align-items-center justify-content-end">
							<a href="signin.html" class="account">
								Sign in <br>
								<span class="font-weight-bold">My Account</span>
							</a>
							<a href="#" class="cart d-flex align-items-center pl-5">
								<span class="cart-count">
									<i class="mdi mdi-cart-outline"></i>
									<span class="count-num">0</span>
								</span>
								<div class="cash">
									My Cart <br>
									<span class="font-weight-bold">$0.00</span>
								</div>
							</a>
						</div>
					</div>
				</div>
			</div>
		</div>
		<!-- /main header-->
	</header>
	<!-- /header -->
</template>

<script>
export default {
    data() {
        return {
            logo: require('../assets/img/makeup-world-bd-logo.jpg'),
            isActive: false,
            makeup: [
            	  {
            	    "id": 5,
            	    "shop_id": 1,
            	    "name": "Category Level One",
            	    "position": 1,
            	    "parent_id": 5,
            	    "category_url": "category_one",
            	    "meta_title": "category_one",
            	    "meta_key": "category_one",
            	    "meta_details": "category_one",
            	    "status": 1,
            	    "created_at": "2020-04-26 00:25:07",
            	    "updated_at": "2020-04-26 00:25:07"
            	  },
            	  {
            	    "id": 6,
            	    "shop_id": 1,
            	    "name": "Category Level Two",
            	    "position": 2,
            	    "parent_id": 6,
            	    "category_url": "category_two",
            	    "meta_title": "Category Title",
            	    "meta_key": "Category Key",
            	    "meta_details": "Category Details",
            	    "status": 1,
            	    "created_at": "2020-04-26 00:25:38",
            	    "updated_at": "2020-04-26 00:25:38"
            	  },
            	  {
            	    "id": 13,
            	    "shop_id": 1,
            	    "name": "Category Level Three",
            	    "position": 2,
            	    "parent_id": 6,
            	    "category_url": "category_three",
            	    "meta_title": "category_three",
            	    "meta_key": "category_three",
            	    "meta_details": "category_three",
            	    "status": 1,
            	    "created_at": "2020-04-08 14:33:19",
            	    "updated_at": "2020-04-08 14:33:19"
            	  },
            	  {
            	    "id": 16,
            	    "shop_id": 1,
            	    "name": "CURRENT OFFER",
            	    "position": 0,
            	    "parent_id": 16,
            	    "category_url": "CURRENT_OFFER",
            	    "meta_title": "CURRENT OFFER",
            	    "meta_key": "CURRENT OFFER",
            	    "meta_details": "CURRENT OFFER",
            	    "status": 1,
            	    "created_at": "2020-05-05 11:09:40",
            	    "updated_at": "2020-05-05 11:09:40"
            	  },
            	  {
            	    "id": 18,
            	    "shop_id": 1,
            	    "name": "Category Level Three",
            	    "position": 2,
            	    "parent_id": 6,
            	    "category_url": "category_threeaaaaaaaaa",
            	    "meta_title": "category_threeaaaaa",
            	    "meta_key": "category_threeaaaaaaaaa",
            	    "meta_details": "category_threeaaaaaaaaaa",
            	    "status": 1,
            	    "created_at": "2020-03-08 03:56:05",
            	    "updated_at": "2020-03-08 06:44:29"
            	  },
            	  {
            	    "id": 21,
            	    "shop_id": 1,
            	    "name": "50% Off",
            	    "position": 1,
            	    "parent_id": 16,
            	    "category_url": "50%_Off",
            	    "meta_title": "50% Off",
            	    "meta_key": "50% Off",
            	    "meta_details": "50% Off",
            	    "status": 1,
            	    "created_at": "2020-05-05 11:18:04",
            	    "updated_at": "2020-05-05 11:18:04"
            	  },
            	  {
            	    "id": 27,
            	    "shop_id": 1,
            	    "name": "Buy 1 Get 1 Free",
            	    "position": 1,
            	    "parent_id": 16,
            	    "category_url": "Buy_1_Get_1_Free_nnnn",
            	    "meta_title": "Buy 1 Get 1 Free",
            	    "meta_key": "Buy 1 Get 1 Free",
            	    "meta_details": "Buy 1 Get 1 Free",
            	    "status": 1,
            	    "created_at": "2020-05-05 11:21:16",
            	    "updated_at": "2020-05-05 11:21:16"
            	  }
            ],
            kachabazar: [
              {
                "id": 1,
                "shop_id": 1,
                "name": "Ramadan",
                "position": 0,
                "parent_id": null,
                "category_url": "Ramadan",
                "meta_title": "Ramadan",
                "meta_key": "Ramadan",
                "meta_details": "Ramadan",
                "status": 1,
                "created_at": "2020-04-29 17:27:55",
                "updated_at": "2020-04-29 17:27:55",
                "category_image": {
                  "id": 11,
                  "shop_id": 1,
                  "products_id": 1,
                  "name": "http://localhost/makeup/include/storage/app/public/kachabazar/2020-04-29-5ea9b91b0e29b.jpg",
                  "type": 4,
                  "height": 460,
                  "width": 680,
                  "status": 1,
                  "created_at": "2020-04-29 17:27:55",
                  "updated_at": "2020-04-29 17:27:55"
                }
              },
              {
                "id": 2,
                "shop_id": 1,
                "name": "SODAYKORI",
                "position": 0,
                "parent_id": null,
                "category_url": "SODAYKORI",
                "meta_title": "SODAYKORI",
                "meta_key": "SODAYKORI",
                "meta_details": "SODAYKORI",
                "status": 1,
                "created_at": "2020-05-05 10:31:55",
                "updated_at": "2020-05-05 10:31:55",
                "category_image": {
                  "id": 12,
                  "shop_id": 1,
                  "products_id": 2,
                  "name": "http://localhost/makeup/include/storage/app/public/kachabazar/2020-04-29-5ea9b9fc4c356.jpg",
                  "type": 4,
                  "height": 460,
                  "width": 680,
                  "status": 1,
                  "created_at": "2020-04-29 17:31:40",
                  "updated_at": "2020-04-29 17:31:40"
                }
              },
              {
                "id": 3,
                "shop_id": 1,
                "name": "Fruit",
                "position": 1,
                "parent_id": 2,
                "category_url": "Fruit",
                "meta_title": "Fruit",
                "meta_key": "Fruit",
                "meta_details": "Fruit",
                "status": 1,
                "created_at": "2020-04-29 17:34:32",
                "updated_at": "2020-04-29 17:34:32",
                "category_image": {
                  "id": 13,
                  "shop_id": 1,
                  "products_id": 3,
                  "name": "http://localhost/makeup/include/storage/app/public/kachabazar/2020-04-29-5ea9baa86fdef.jpg",
                  "type": 4,
                  "height": 460,
                  "width": 680,
                  "status": 1,
                  "created_at": "2020-04-29 17:34:32",
                  "updated_at": "2020-04-29 17:34:32"
                }
              },
              {
                "id": 4,
                "shop_id": 1,
                "name": "Fresh Fruits",
                "position": 2,
                "parent_id": 3,
                "category_url": "Fresh Fruits",
                "meta_title": "Fresh Fruits",
                "meta_key": "Fresh Fruits",
                "meta_details": "Fresh Fruits",
                "status": 1,
                "created_at": "2020-04-29 17:35:12",
                "updated_at": "2020-04-29 17:35:12",
                "category_image": {
                  "id": 14,
                  "shop_id": 1,
                  "products_id": 4,
                  "name": "http://localhost/makeup/include/storage/app/public/kachabazar/2020-04-29-5ea9bad0a3f3d.jpg",
                  "type": 4,
                  "height": 460,
                  "width": 680,
                  "status": 1,
                  "created_at": "2020-04-29 17:35:12",
                  "updated_at": "2020-04-29 17:35:12"
                }
              },
              {
                "id": 5,
                "shop_id": 1,
                "name": "Fruits and Vegetables",
                "position": 1,
                "parent_id": 2,
                "category_url": "Fruits_and_Vegetables",
                "meta_title": "Fruits and Vegetables",
                "meta_key": "Fruits and Vegetables",
                "meta_details": "Fruits and Vegetables",
                "status": 1,
                "created_at": "2020-05-05 15:12:01",
                "updated_at": "2020-05-05 15:12:01",
                "category_image": {
                  "id": 18,
                  "shop_id": 1,
                  "products_id": 5,
                  "name": "https://mwbddemo.com/admin/include/storage/app/public/kachabazar/2020-05-05-5eb0edf3bc0c0.jpg",
                  "type": 4,
                  "height": 460,
                  "width": 680,
                  "status": 1,
                  "created_at": "2020-05-05 10:39:15",
                  "updated_at": "2020-05-05 10:39:15"
                }
              },
              {
                "id": 6,
                "shop_id": 1,
                "name": "Meat and Fish",
                "position": 1,
                "parent_id": 2,
                "category_url": "Meat_and_Fish",
                "meta_title": "Meat and Fish",
                "meta_key": "Meat and Fish",
                "meta_details": "Meat and Fish",
                "status": 1,
                "created_at": "2020-05-05 10:46:37",
                "updated_at": "2020-05-05 10:46:37",
                "category_image": {
                  "id": 19,
                  "shop_id": 1,
                  "products_id": 6,
                  "name": "https://mwbddemo.com/admin/include/storage/app/public/kachabazar/2020-05-05-5eb0efad8fe20.jpg",
                  "type": 4,
                  "height": 460,
                  "width": 680,
                  "status": 1,
                  "created_at": "2020-05-05 10:46:37",
                  "updated_at": "2020-05-05 10:46:37"
                }
              },
              {
                "id": 8,
                "shop_id": 1,
                "name": "Cooking",
                "position": 1,
                "parent_id": 2,
                "category_url": "Cooking",
                "meta_title": "Cooking",
                "meta_key": "Cooking",
                "meta_details": "Cooking",
                "status": 1,
                "created_at": "2020-05-05 15:13:52",
                "updated_at": "2020-05-05 15:13:52",
                "category_image": {
                  "id": 21,
                  "shop_id": 1,
                  "products_id": 8,
                  "name": "https://mwbddemo.com/admin/include/storage/app/public/kachabazar/2020-05-05-5eb12e5062bdc.jpeg",
                  "type": 4,
                  "height": 460,
                  "width": 680,
                  "status": 1,
                  "created_at": "2020-05-05 15:13:52",
                  "updated_at": "2020-05-05 15:13:52"
                }
              },
              {
                "id": 9,
                "shop_id": 1,
                "name": "Rice",
                "position": 2,
                "parent_id": 8,
                "category_url": "Rice",
                "meta_title": "Rice",
                "meta_key": "Rice",
                "meta_details": "Rice",
                "status": 1,
                "created_at": "2020-05-05 15:18:52",
                "updated_at": "2020-05-05 15:18:52",
                "category_image": {
                  "id": 22,
                  "shop_id": 1,
                  "products_id": 9,
                  "name": "https://mwbddemo.com/admin/include/storage/app/public/kachabazar/2020-05-05-5eb12f7cf3454.jpeg",
                  "type": 4,
                  "height": 460,
                  "width": 680,
                  "status": 1,
                  "created_at": "2020-05-05 15:18:52",
                  "updated_at": "2020-05-05 15:18:53"
                }
              },
              {
                "id": 10,
                "shop_id": 1,
                "name": "Oil",
                "position": 2,
                "parent_id": 8,
                "category_url": "Oil",
                "meta_title": "Oil",
                "meta_key": "Oil",
                "meta_details": "Oil",
                "status": 1,
                "created_at": "2020-05-05 15:21:05",
                "updated_at": "2020-05-05 15:21:05",
                "category_image": {
                  "id": 23,
                  "shop_id": 1,
                  "products_id": 10,
                  "name": "https://mwbddemo.com/admin/include/storage/app/public/kachabazar/2020-05-05-5eb13001cce82.jpeg",
                  "type": 4,
                  "height": 460,
                  "width": 680,
                  "status": 1,
                  "created_at": "2020-05-05 15:21:05",
                  "updated_at": "2020-05-05 15:21:05"
                }
              }
            ]
                
        }
	},
	methods: {
		handleSCroll(event) {
			let header = document.querySelector(".header");
			if (window.scrollY > 75 && !header.className.includes("header-fixed")) {
				header.classList.add("header-fixed");
			} else if (window.scrollY < 75) {
				header.classList.remove("header-fixed");
			}
		}
	},
	created() {
		window.addEventListener("scroll", this.handleSCroll);
	},
	destroyed() {
		window.removeEventListener("scroll", this.handleSCroll);
	}
}
</script>

<style>

</style>