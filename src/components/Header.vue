<template>
	<div class="header" >
			<!-- Topbar -->
			<div class="topbar">
				<div class="container">
					<div class="row">
						
						<div class="col-lg-12 col-md-7 col-12">
							<!-- Top Contact -->
							<ul class="top-contact">
								<li><i class="fa fa-phone"></i>834 166-7859</li>
								<li><i class="fa fa-envelope"></i><a href="mailto:info@cooldent.com">info@cooldent.com</a></li>
							</ul>
							<!-- End Top Contact -->
						</div>
					</div>
				</div>
			</div>
			<!-- End Topbar -->
			<!-- Header Inner -->
			<div class="header-inner">
				<div class="container">
					<div class="inner">
						<div class="row">
							<div class="col-lg-3 col-md-3 col-12">
								<!-- Start Logo -->
								<div class="logo">
									<a href="/"><img src="../assets/img/logo-vectorized.png" alt="#"></a>
								</div>
								<!-- End Logo -->
								<!-- Mobile Nav -->
								<div class="mobile-nav"></div>
								<!-- End Mobile Nav -->
							</div>
							<div class="col-lg-7 col-md-9 col-12">
								<!-- Main Menu -->
								<div class="main-menu">
									<nav class="navigation">
										<ul class="nav menu">
											<!-- <li><a href="#">Doctores </a></li> -->
											<li><a href="#/" @click="scrollTo('services')">Servicios </a></li>
											<li><a href="#/" @click="scrollTo('pricing-table')">Precios </a></li>
											<li><a href="#/about">Info</a></li>
										</ul>
									</nav>
								</div>
								<!--/ End Main Menu -->
							</div>
							<div class="col-lg-2 col-12">
								<div class="get-quote">
									<a href="#/appointment" class="btn">Agenda tu cita</a>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
			
		</div>

</template>

<script>
	export default {
		methods: {
			scrollTo(name = "slider") {
				const element = document.getElementById(name);

				element.scrollIntoView({ behavior: "smooth", block: "start", inline: "nearest" });
			}
		}
	}
</script>

<style scoped>
.btn {
	color: white;
}
</style>