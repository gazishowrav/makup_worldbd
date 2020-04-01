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
				        <a class="nav-link" href="index.html">Home <span class="sr-only">(current)</span></a>
				      </li>
				      <li class="nav-item">
				        <a class="nav-link" href="products.html">Current Offers</a>
				      </li>
				      <li class="nav-item">
				        <a class="nav-link" href="products.html">All Categories</a>
				      </li>
				      <li class="nav-item">
				        <a class="nav-link" href="products.html">Whitening</a>
				      </li>
				      <li class="nav-item">
				        <a class="nav-link" href="products.html">Slimming</a>
				      </li>
				      <li class="nav-item">
				        <a class="nav-link" href="products.html">Beauty Tips</a>
				      </li>
				      <li class="nav-item">
				        <a class="nav-link" href="products.html">Contact</a>
				      </li>
				      <li class="nav-item">
				        <a class="nav-link" href="products.html">Pre-Order</a>
				      </li>
				      <li class="nav-item">
				        <a class="nav-link" href="products.html">Suggest Products</a>
				      </li>
				    </ul>
				    <ul class="navbar-nav ml-auto social-menu">
				      <li class="nav-item">
				        <a href="#" class="nav-link"><i class="mdi mdi-facebook"></i></a>
				      </li>
				      <li class="nav-item">
				        <a href="#" class="nav-link"><i class="mdi mdi-instagram"></i></a>
				      </li>
				      <li class="nav-item">
				        <a href="#" class="nav-link"><i class="mdi mdi-youtube"></i></a>
				      </li>
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
						<div class="btn-catagory">
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
            logo: require('../assets/img/makeup-world-bd-logo.jpg')
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