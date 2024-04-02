<script>
import valoracionSVG from '../assets/img/svg/valoracion.svg'
import extraccionSVG from '../assets/img/svg/extraccion.svg'
import carieSVG from '../assets/img/svg/carie.svg'
import ortodonciaSVG from '../assets/img/svg/ortodoncia.svg'
import teethWhiteningSVG from '../assets/img/svg/teeth-whitening.svg'
import limpiezaSVG from '../assets/img/svg/limpieza.svg'
import reconstruccionSVG from '../assets/img/svg/reconstruccion.svg'

export default {
  data(){
    return {
      valoracionSVG, extraccionSVG, carieSVG, ortodonciaSVG, teethWhiteningSVG, limpiezaSVG, reconstruccionSVG
    }
  }
}
</script>

<template>
    <section id="services" class="services section">
			<div class="container">
				<div class="row">
					<div class="col-lg-12">
						<div class="section-title">
							<h2>Ofrecemos diferentes servicios para ayudarte a tener tu sonrisa ideal.</h2>
							<span>---</span><img src="/favicon.ico" alt="#" style="width: 40px;"><span>---</span>
						</div>
					</div>
				</div>
				<div class="row">
					<div class="col-lg-4 col-md-6 col-12">
						<!-- Start Single Service -->
						<div class="single-service">
							<!-- <i><object data="../assets/img/valoracion.svg" width="40" height="40"> </object></i> -->
              <i><img :src="valoracionSVG" style="width: 50px;"/></i>
							<h4><a >Valoracion General</a></h4>
							<p>Desde la salud de tus dientes hasta la alineación de tu mordida, nos aseguramos de proporcionarte una visión clara de tu salud bucal actual y cualquier tratamiento necesario para mantener tu sonrisa radiante y saludable. </p>	
						</div>
						<!-- End Single Service -->
					</div>
					<div class="col-lg-4 col-md-6 col-12">
						<!-- Start Single Service -->
						<div class="single-service">
							<i><img :src="teethWhiteningSVG" style="width: 50px;"/></i>
							<h4><a>Blaqueamiento dental</a></h4>
							<p>Utilizando tecnología avanzada y productos de alta calidad, logramos devolverle a tu sonrisa su brillo natural en poco tiempo. ¡Dale a tus dientes un aspecto más brillante y radiante con nuestro blanqueamiento dental profesional! </p>	
						</div>
						<!-- End Single Service -->
					</div>
					<div class="col-lg-4 col-md-6 col-12">
						<!-- Start Single Service -->
						<div class="single-service">
							<i><img :src="ortodonciaSVG" style="width: 50px;"/></i>
							<h4><a >Tratamiento de ortodoncia</a></h4>
							<p>Un tratamiento de ortodoncia es la clave para una sonrisa recta y saludable. Con técnicas avanzadas y dispositivos innovadores, corregimos la alineación de tus dientes y mandíbula para mejorar tu apariencia y función dental. ¡Descubre cómo nuestra ortodoncia puede transformar tu sonrisa y tu confianza! </p>	
						</div>
						<!-- End Single Service -->
					</div>
					<div class="col-lg-4 col-md-6 col-12">
						<!-- Start Single Service -->
						<div class="single-service">
							<i><img :src="extraccionSVG" style="width: 50px;"/></i>
							<h4><a >Extracciones</a></h4>
							<p>Una extracción dental es un procedimiento rápido y seguro para eliminar un diente problemático o dañado. Con cuidado y precisión, nuestro equipo experto garantiza una experiencia cómoda y sin dolor. Recupera la salud y el bienestar bucal con nuestra extracción dental confiable y eficaz. </p>	
						</div>
						<!-- End Single Service -->
					</div>
					<div class="col-lg-4 col-md-6 col-12">
						<!-- Start Single Service -->
						<div class="single-service">
							<i><img :src="reconstruccionSVG" style="width: 50px;"/></i>
							<h4><a >Reconstrucción dental</a></h4>
							<p>La reconstrucción dental es un procedimiento restaurador que devuelve la forma y función a tus dientes dañados o perdidos. Utilizando técnicas avanzadas y materiales de alta calidad, nuestro equipo experto reconstruye tu sonrisa para que luzca natural y saludable. ¡Recupera tu confianza y funcionalidad oral con nuestra reconstrucción dental de primera clase! </p>	
						</div>
						<!-- End Single Service -->
					</div>
					<div class="col-lg-4 col-md-6 col-12">
						<!-- Start Single Service -->
						<div class="single-service">
							<i><img :src="carieSVG" style="width: 43px;"/></i>
							<h4><a >Caries</a></h4>
							<p>Con técnicas avanzadas y materiales de calidad, nuestro equipo experto elimina las caries y rellena el área afectada para devolver la función y la estética a tu sonrisa. ¡Recupera la salud dental con nuestra reparación de caries profesional! </p>	
						</div>
						<!-- End Single Service -->
					</div>
				</div>
			</div>
		</section>
</template>