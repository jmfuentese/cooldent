<template>
	<div id="contact-us-section">
		<div class="breadcrumbs overlay">
			<div class="container">
				<div class="bread-inner">
					<div class="row">
						<div class="col-12">
							<h2>Encuentranos</h2>
							<ul class="bread-list">
								<li><a href="#/">Inicio</a></li>
								<li><i class="fa-solid fa-angle-right"></i></li>
								<li class="active">Info</li>
							</ul>
						</div>
					</div>
				</div>
			</div>
		</div>
		<!-- End Breadcrumbs -->
				
		<!-- Start Contact Us -->
		<section class="contact-us section">
			<div class="container">
				<div class="inner">
					<div class="row"> 
						<div class="col-lg-6">
							<div class="map-container">
								<img class="map" src="../assets/img/map.png" alt="">
							</div>
						</div>
						<div class="col-lg-6">
							<div class="contact-us-form">
								<h2>Contactanos</h2>
								<p>Si tienes alguna duda porfavor sientete libre de contactarnos.</p>
								<!-- Form -->
								<form class="form" method="post" action="mail/mail.php">
									<div class="row">
										<div class="col-lg-6">
											<div class="form-group">
												<input type="text" name="name" placeholder="Name" required>
											</div>
										</div>
										<div class="col-lg-6">
											<div class="form-group">
												<input type="email" name="email" placeholder="Email" required>
											</div>
										</div>
										<div class="col-lg-6">
											<div class="form-group">
												<input type="text" name="phone" placeholder="Phone" required>
											</div>
										</div>
										<div class="col-lg-6">
											<div class="form-group">
												<input type="text" name="subject" placeholder="Subject" required>
											</div>
										</div>
										<div class="col-lg-12">
											<div class="form-group">
												<textarea name="message" placeholder="Your Message" required></textarea>
											</div>
										</div>
										<div class="col-12">
											<div class="form-group login-btn">
												<button class="btn" type="submit">Send</button>
											</div>
											<div class="checkbox">
												<label class="checkbox-inline" for="2"><input name="news" id="2" type="checkbox">Quieres suscribir tu correo para recibir promociones?</label>
											</div>
										</div>

									</div>
								</form>
								<!--/ End Form -->
							</div>
						</div>
					</div>
				</div>
				<div class="contact-info">
					<div class="row">
						<!-- single-info -->
						<div class="col-lg-4 col-12 ">
							<div class="single-info">
								<i class="fa-solid fa-phone"></i>
								<div class="content">
									<h3>+(52) 834 166-7859</h3>
									<p>info@cooldent.com</p>
								</div>
							</div>
						</div>
						<!--/End single-info -->
						<!-- single-info -->
						<div class="col-lg-4 col-12 ">
							<div class="single-info">
								<i class="fa-solid fa-location-dot"></i>
								<div class="content">
									<h3>Blvrd Praxedis Balboa 1013-7 Y 8, Zona Centro</h3>
									<p>87000 Cd. Victoria, Tamps.</p>
								</div>
							</div>
						</div>
						<!--/End single-info -->
						<!-- single-info -->
						<div class="col-lg-4 col-12 ">
							<div class="single-info">
								<i class="fa-solid fa-calendar-days"></i>
								<div class="content">
									<h3>Lunes a Domingo</h3>
									<p>Abierto todos los días</p>
								</div>
							</div>
						</div>
						<!--/End single-info -->
					</div>
				</div>
			</div>
		</section>
	</div>
</template>

<script>
	export default {
		methods: {
			scrollToTop(){
				const element = document.getElementById("contact-us-section");

				element.scrollIntoView({ behavior: "smooth", block: "start", inline: "nearest" });
			},
		},
		mounted() {
			this.scrollToTop()
		}
	}
</script>

<style scoped>
.map-container {
	text-align: center;
	padding: 60px 20px;
}
</style>