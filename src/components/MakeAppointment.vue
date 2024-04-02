<template>
  <section id="calendar-section" class="section">
    <div class="container">
      <div class="inner">
        <div class="row calendar-title">
          <div class="col-lg-12">
            <h4>Selecciona el día en el calendario y llena los detalles de tu cita </h4>
          </div>
        </div>
        <div class="row">
          <div class="calendar col-lg-6">
            <div class="calendar-header">
              <button @click="previousMonth" class="month-btn btn-primary">&lt;</button>
              <h3>{{ currentMonth }}</h3>
              <button @click="nextMonth" class="month-btn btn-primary">&gt;</button>
            </div>
            <ol class="days">
              <li class="day-name">Domingo</li>
              <li class="day-name">Lunes</li>
              <li class="day-name">Martes</li>
              <li class="day-name">Miércoles</li>
              <li class="day-name">Jueves</li>
              <li class="day-name">Viernes</li>
              <li class="day-name">Sábado</li>
              <li 
                data-bs-toggle="tooltip" data-bs-placement="top"
                data-bs-custom-class="custom-tooltip"
                data-bs-title="This top tooltip is themed via CSS variables."
                v-for="(day, index) in daysInMonth" 
                :key="index" @click="selectDay(day)" 
                :class="['calendar-day', getDayClass(day, index), { 'selected-day': isCurrentDaySelected(day.rawDate)}, getFirstDayClass(day.date, index)]">
                {{ index + 1 }}
                <!-- <button v-if="day.availability < 10" @click="scheduleAppointment(day.date)" class="schedule-button">Agendar</button> -->
                <!-- <p v-if="isCurrentDay(day.rawDate)" style="font-weight: bold; color: white;">Hoy</p> -->
              </li>
            </ol>
            <p style="text-align: left; font-weight: bold;">Disponibilidad:</p>
            <ol class="legend">
              <li><div class="legend-1"></div> Alta</li>
              <li><div class="legend-2"></div> Media</li>
              <li><div class="legend-3"></div> Baja</li>
              <li><div class="legend-4"></div> Sin Disponibilidad</li>
              <li><div class="legend-5"></div> Día no válido</li>
            </ol>
          </div>
          <div class="schedule-form col-lg-6">
            <h3>Detalles de tu cita</h3>
            <form class="g-3 needs-validation" novalidate>
              <div class="row">
                <div class="col-lg-5">
                  <label for="validationCustom04" class="form-label">Horario</label>
                  <div class="select-wrapper">
                    <select class="form-select form-select-lg" name="schedule" id="" required>
                      <option selected disabled value="">Horario</option>
                      <option value="1">8:00am - 9:00am</option>
                      <option value="2">9:00am - 10:00am</option>
                      <option value="3">10:00am - 11:00am</option>
                      <option value="4">11:00am - 12:00pm</option>
                      <option value="5">12:00pm - 1:00pm</option>
                      <option value="6">3:00pm - 4:00pm</option>
                      <option value="7">4:00pm - 5:00pm</option>
                      <option value="8">5:00pm - 6:00pm</option>
                      <option value="9">6:00pm - 7:00pm</option>
                      <option value="10">7:00pm - 8:00pm</option>
                    </select>
                    <div class="invalid-feedback">
                      Porfavor selecciona un horario
                    </div>
                  </div>
                </div>
                <div class="col-lg-7">
                  <div class="mb-3">
                    <label for="validationCustom06" class="form-label">Fecha</label>
                    <input type="text" class="form-control" :value="selectedDay.toLocaleString('es-ES', { weekday: 'long', day: 'numeric', year: 'numeric', month: 'long'}) " disabled>
                  </div>
                </div>
                <div class="col-lg-12">
                  <label for="validationCustom05" class="form-label">Motivo de tu cita</label>
                  <select name="service" class="form-select form-select-lg" required>
                    <option selected disabled value="">Selecciona el servicio</option>
                    <option value="">Limpieza dental</option>
                    <option value="">Inicio de ortodoncia y valoración</option>
                    <option value="">Blanqueamiento dental</option>
                    <option value="">Tratamiento de caries</option>
                    <option value="">Ajuste de ortodoncia</option>
                    <option value="">Extracción dental</option>
                    <option value="">Reconstrucción con resina</option>
                  </select>
                  <div class="invalid-feedback">
                    Porfavor selecciona un servicio
                  </div>
                </div>
                
                <div class="col-lg-6">
                  <label for="validationCustom01" class="form-label">Nombre completo</label>
                  <input type="text" name="name" class="form-control" id="validationCustom01" required>
                  <div class="invalid-feedback">
                    Llena este campo con tu nombre
                  </div>
                </div>
                <div class="col-lg-6">
                  <label for="validationCustom02" class="form-label">Email</label>
                  <input type="email" name="email" class="form-control" id="validationCustom02" required>
                  <div class="invalid-feedback">
                    Porfavor introduce un email válido
                  </div>
                </div>
                <div class="col-lg-6">
                  <label for="validationCustom03" class="form-label">Teléfono</label>
                  <input type="text" name="phone" class="form-control" id="validationCustom03" required>
                  <div class="invalid-feedback">
                    Verifica tu teléfono
                  </div>
                </div>
              </div>
            </form>
            <div class="col-12">
              <button class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#confirmation-modal" >Agendar</button>
            </div>
          </div>
          
        </div>
      </div>
    </div>
  </section>

  <div id="confirmation-modal" class="modal" tabindex="-1">
		<div class="modal-dialog modal-dialog-centered">
			<div class="modal-content">
				<div class="modal-header">
					<h5 class="modal-title">Confirma los datos de tu cita:</h5>
					<button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
				</div>
				<div class="modal-body">
					<p>Modal body text goes here.</p>
				</div>
				<div class="modal-footer">
					<button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Cancelar</button>
					<button type="button" class="btn btn-primary">Confirmar</button>
				</div>
			</div>
		</div>
	</div>
</template>
  
  <script>
  export default {
    data() {
      return {
        currentDate: new Date(),
        daysInMonth: [],
        selectedDay: ''
      };
    },
    computed: {
      currentMonth() {
        return this.currentDate.toLocaleString('es-ES', { month: 'long', year: 'numeric' });
      }
    },
    methods: {
      formValidation(){
        'use strict'

        // Fetch all the forms we want to apply custom Bootstrap validation styles to
        const forms = document.querySelectorAll('.needs-validation')

        // Loop over them and prevent submission
        Array.from(forms).forEach(form => {
          form.addEventListener('submit', event => {
            if (!form.checkValidity()) {
              event.preventDefault()
              event.stopPropagation()
            }

            form.classList.add('was-validated')
          }, false)
        })
      },
      scrollToTop(){
        const element = document.getElementById("calendar-section");

        element.scrollIntoView({ behavior: "smooth", block: "start", inline: "nearest" });
      },
      generateCalendar() {
        const firstDayOfMonth = new Date(this.currentDate.getFullYear(), this.currentDate.getMonth(), 1);
        const lastDayOfMonth = new Date(this.currentDate.getFullYear(), this.currentDate.getMonth() + 1, 0);
  
        this.daysInMonth = [];

        let firstDay = 0;
  
        for (let i = firstDayOfMonth.getDate(); i <= lastDayOfMonth.getDate(); i++) {
          const currentDate = new Date(this.currentDate.getFullYear(), this.currentDate.getMonth(), i);
          const availability = this.calculateAvailability(); // Implement your logic to calculate availability
          this.daysInMonth.push({ rawDate: currentDate, date: currentDate.toLocaleString('es-ES', { weekday: 'long', day: 'numeric' }), availability, firstDay});
        }
      },
      calculateAvailability() {
        // Implement your logic to calculate availability for the given date
        // For this example, let's assume random availability between 0 and 10
        return Math.floor(Math.random() * 11); // Generates random number between 0 and 10
      },
      getFirstDayClass(date, index){
        if (index === 0){
          const day = date.split(" ")[0]
          if (day === "domingo") {
            return 'first-day-1';
          } else if (day === "lunes") {
            return 'first-day-2';
          }
          else if (day === "martes") {
            return 'first-day-3';
          }
          else if (day === "miércoles") {
            return 'first-day-4';
          }
          else if (day === "jueves") {
            return 'first-day-5';
          }
          else if (day === "viernes") {
            return 'first-day-6';
          }
          else if (day === "sábado") {
            return 'first-day-7';
          }
        }
      },
      isInvalidDay(rawDate){
        const today = new Date();
        if (rawDate < today){
          return true;
        }else{
          return false;
        }
      },
      selectDay(day) {
        if (day.availability < 10 && !this.isInvalidDay(day.rawDate)){
          this.selectedDay = day.rawDate;
          return true;
        }
        return false;
      },
      getDayClass(day) {
        const availability = day.availability
        
        if (this.isInvalidDay(day.rawDate)){
          return 'invalid-day';
        }
        if (availability >= 0 && availability < 5) {
            return 'high-availability';
        } else if (availability >= 5 && availability < 7) {
            return 'medium-availability';
        } else if (availability >= 7 && availability < 10) {
            return 'low-availability';
        } else if (availability === 10) {
            return 'no-availability';
        }
      },
      isCurrentDaySelected(date) {
        const selected = this.selectedDay.toLocaleString('es-ES', { weekday: 'long', day: 'numeric', year: 'numeric', month: 'long'});
        return date.toLocaleString('es-ES', { weekday: 'long', day: 'numeric', year: 'numeric', month: 'long'}) === selected;
      },
      isDateAvailable() {
        // Implement your logic to check availability for the given date
        // This could involve checking against your database of appointments
        // For this example, let's assume all dates are available
        return true;
      },
      previousMonth() {
        this.currentDate = new Date(this.currentDate.getFullYear(), this.currentDate.getMonth() - 1, 1);
        this.generateCalendar();
      },
      nextMonth() {
        this.currentDate = new Date(this.currentDate.getFullYear(), this.currentDate.getMonth() + 1, 1);
        this.generateCalendar();
      },
      scheduleAppointment(date) {
        // Implement logic to schedule appointment for the selected date
        console.log("Appointment scheduled for:", date);
      }
    },
    mounted() {
      this.generateCalendar();
      this.scrollToTop();
      this.formValidation();
    }
  };
  </script>
  
  <style scoped>
  .custom-tooltip {
    --bs-tooltip-bg: #1B3E9F;
    --bs-tooltip-color: white;
  }
  input {
    width: 100%;
    height: 50px;
    border: 1px solid #eee;
    padding: 0px 18px;
    color: #555;
    font-size: 14px;
    font-weight: 400;
    border-radius: 4px;
  }
  .inner {
    box-shadow: 0px 0px 10px #00000024;
    border-radius: 5px;
    overflow:hidden;
  }
  .high-availability {
    background-color: #19E680; /* Verde */
  }

  .medium-availability {
    background-color: #C9F836; /* Amarillo */
  }

  .low-availability {
    background-color: #FE9559; /* Naranja */
  }

  .no-availability {
    background-color: #EE4D4D; /* Rojo */
  }
  .invalid-day {
    background-color: #CDCDCD;
  }
  .schedule-form {
    padding: 10px 30px;
  }
  .schedule-form h3 {
    position: relative;
    font-size: 24px;
    color: #333;
    font-weight: 600;
    line-height: 27px;
    text-transform: capitalize;
    margin: 30px 0;
    padding-bottom: 20px;
    text-align: left;
  }
  .schedule-form h3:before {
    position:absolute;
    content:"";
    left:0;
    bottom:0;
    height:2px;
    width:50px;
    background:#1A76D1;
  }
  .calendar-title {
    margin-top: 50px;
    padding: 20px;
    text-align: center;
  }
  .calendar {
    border-radius: 5px;
    margin: 0;
    padding: 30px;
  }
  
  .calendar-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 10px;
  }
  .legend {
    display: flex;
    gap: 15px;
    font-size: 10px;
  }
  .legend-1 {
    background-color: #19E680;
    display: inline-block;
    width: 10px;
    height: 10px;
    border-radius: 20%;
  }
  .legend-2 {
    background-color: #C9F836;
    display: inline-block;
    width: 10px;
    height: 10px;
    border-radius: 20%;
  }
  .legend-3 {
    background-color: #FE9559;
    display: inline-block;
    width: 10px;
    height: 10px;
    border-radius: 20%;
  }
  .legend-4 {
    background-color: #EE4D4D;
    display: inline-block;
    width: 10px;
    height: 10px;
    border-radius: 20%;
  }
  .legend-5 {
    background-color: #CDCDCD;
    display: inline-block;
    width: 10px;
    height: 10px;
    border-radius: 20%;
  }
  
  .days {
    display: grid;
    grid-template-columns: repeat(7, 1fr); /* Ajusta automáticamente el número de columnas dependiendo del tamaño de la pantalla */
    gap: 5px;
    list-style: none;
    padding: 0;
  }
  
  .calendar-day {
    border: 1px solid #ccc;
    color: #fff;
    border-radius: 5px;
    width: 100%;
    height: 70px;
    padding: 5px;
    text-align: center;
  }

  .selected-day {
    animation: pulse 1s infinite alternate; /* Animación de destello */
  }

  @keyframes pulse {
    from {
        border-color: transparent;
        box-shadow: 0 0 10px #0051FF; /* Color verde */
    }
    to {
        border-color: transparent;
        box-shadow: 0 0 25px #0051FF; /* Color verde */
    }
  }
  .day-name {
    text-align: center;
    font-weight: bold;
  }
  .first-day-1 {
    grid-column-start: 1;
  }
  .first-day-2 {
    grid-column-start: 2;
  }
  .first-day-3 {
    grid-column-start: 3;
  }
  .first-day-4 {
    grid-column-start: 4;
  }
  .first-day-5 {
    grid-column-start: 5;
  }
  .first-day-6 {
    grid-column-start: 6;
  }
  .first-day-7 {
    grid-column-start: 7;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  .month-btn {
    width: 20px;
    height: 20px;
  }
  </style>
  