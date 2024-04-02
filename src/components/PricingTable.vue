<script>
import ortodonciaSVG from '../assets/img/svg/ortodoncia.svg'
import limpiezaSVG from '../assets/img/svg/limpieza.svg'
import txSVG from '../assets/img/svg/tx.svg'

export default {
  data(){
    return {
      ortodonciaSVG, limpiezaSVG, txSVG
    }
  }
}
</script>

<template>
	<section id="pricing-table" class="pricing-table section">
		<div class="container">
			<div class="row">
				<div class="col-lg-12">
					<div class="section-title">
						<h2>Te ofrecemos el mejor tratamiento a un precio razonable</h2>
						<span>---</span><img src="/favicon.ico" alt="#" style="width: 40px;"><span>---</span>
					</div>
				</div>
			</div>
			<div class="row">
				<!-- Single Table -->
				<div class="col-lg-4 col-md-12 col-12">
					<div class="single-table">
						<!-- Table Head -->
						<div class="table-head">
							<div class="icon">
								<i><img :src="txSVG" style="width: 60px;"/></i>
							</div>
							<h4 class="title">Inicio Ortodoncia</h4>
							<div class="price">
								<p class="amount">$1200</p>
							</div>	
						</div>
						<!-- Table List -->
						<ul class="table-list">
							<li><i class="fa-solid fa-circle-check"></i>Corrección de la alineación dental</li>
							<li><i class="fa-solid fa-circle-check"></i>Mejora de la mordida</li>
							<li><i class="fa-solid fa-circle-check"></i>Prevención de problemas dentales</li>
							<li><i class="fa-solid fa-circle-check"></i>Mejora de la salud bucal</li>
							<li><i class="fa-solid fa-circle-check"></i>Mejora de la confianza y la autoestima</li>
							<li></li>
						</ul>
						<div class="table-bottom">
							<a class="btn" href="#/appointment">Agendar</a>
						</div>
						<!-- Table Bottom -->
					</div>
				</div>
				<!-- End Single Table-->
				<!-- Single Table -->
				<div class="col-lg-4 col-md-12 col-12">
					<div class="single-table">
						<!-- Table Head -->
						<div class="table-head">
							<div class="icon">
								<i><img :src="limpiezaSVG" style="width: 60px;"/></i>
							</div>
							<h4 class="title">Limpieza dental</h4>
							<div class="price">
								<p class="amount">$500</p>
							</div>	
						</div>
						<!-- Table List -->
						<ul class="table-list">
							<li><i class="fa-solid fa-circle-check"></i>Remoción de placa y sarro</li>
							<li><i class="fa-solid fa-circle-check"></i>Prevención de enfermedades bucales</li>
							<li><i class="fa-solid fa-circle-check"></i>Mejora de la salud bucal</li>
							<li><i class="fa-solid fa-circle-check"></i>Eliminación de manchas superficiales</li>
							<li><i class="fa-solid fa-circle-check"></i>Frescura y sensación de limpieza</li>
						</ul>
						<div class="table-bottom">
							<a class="btn" href="#/appointment">Agendar</a>
						</div>
						<!-- Table Bottom -->
					</div>
				</div>
				<!-- End Single Table-->
				<!-- Single Table -->
				<div class="col-lg-4 col-md-12 col-12">
					<div class="single-table">
						<!-- Table Head -->
						<div class="table-head">
							<div class="icon">
								<i><img :src="ortodonciaSVG" style="width: 60px;"/></i>
							</div>
							<h4 class="title">Ajuste de ortodoncia</h4>
							<div class="price">
								<p class="amount">$350<span>/ Por visita</span></p>
							</div>	
						</div>
						<!-- Table List -->
						<ul class="table-list">
							<li><i class="fa-solid fa-circle-check"></i>Valoración general</li>
							<li><i class="fa-solid fa-circle-check"></i>Revision general del progreso</li>
							<li><i class="fa-solid fa-circle-check"></i>Cambio de ligas</li>
							<li><i class="fa-solid fa-circle-check"></i>Reemplazo de alambre</li>
							<li><i class="fa-solid fa-circle-check"></i>Rectificación de posición de brackets</li>
							<li></li>
						</ul>
						<div class="table-bottom">
							<a class="btn" href="#/appointment">Agendar</a>
						</div>
						<!-- Table Bottom -->
					</div>
				</div>
				<!-- End Single Table-->
			</div>	
		</div>	
	</section>	
</template>