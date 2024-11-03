<script>
import Boton from './Boton.vue';
import Swal from 'sweetalert2';

export default {
  name: 'FormularioAsistencia',
  data() {
    return {
      section: 'CONFIRMAR ASISTENCIA',
      title: '¿Asistiré a la fiesta?',
      titleSect1: 'ASISTIRÉ:',
      datos:'DATOS PERSONALES:',
      limite:'(Tenés tiempo hasta el 29 de noviembre)',
      options1: 'Sí',
      options2: 'No',
      inputName: 'Nombre completo:',
      inputTxtArea: 'Información adicional (opcional):',
      isAttending: '',
      nombre: '',
      informacionAdicional: '',
      errorMessage: ''
    }
  },
  components:{
    Boton
  },
  methods: {
        enviarAWhatsApp() {
            if (!this.nombre || !this.isAttending) {
                Swal.fire({
                    title: 'Error!',
                    text: 'Por favor, complete todos los campos requeridos',
                    icon: 'error',
                    confirmButtonText: 'OK'
                });
                return;
            }

            const mensaje = `Nombre: ${this.nombre}\nAsistiré: ${this.isAttending === 'yes' ? 'Sí' : 'No'}\nInformación adicional: ${this.informacionAdicional}`;
            const telefono = "2983614653";
            const enlaceWhatsApp = `https://wa.me/${telefono}?text=${encodeURIComponent(mensaje)}`;

            Swal.fire({
                title: 'Info!',
                text: 'Será redirigido a WhatsApp para confirmar el envío del mensaje.',
                icon: 'info',
                confirmButtonText: 'OK'
            }).then((result) => {
                if (result.isConfirmed) {
                    window.open(enlaceWhatsApp, '_blank');
                }
            });
        }
    },
  computed: {
    isFormIncomplete() {
      return !this.nombre || !this.isAttending;
    }
  }
}
</script>
<template>
    <div id="asistencia" class="containerFormulario" data-aos="fade-up" data-aos-anchor-placement="center-bottom">
        <div class="content_title_formulario">
            <h1 class="titleFormulario">{{ section }}</h1>
        </div>
        <div class="modal-body">
            <div class="-flex flex-column">
                <fieldset>
                    <legend>{{ titleSect1 }}</legend>
                    <div class="form-group mb-3">
                        <label for="" class="title_section"></label>
                        <div class="content__radio">
                            <div class="form-check form-check-inline">
                                <input class="form-check-input" type="radio" id="attendingYes" name="attendance"
                                    v-model="isAttending" value="yes" />
                                <label class="form-check-label" for="attendingYes">{{ options1 }}</label>
                            </div>
                            <div class="form-check form-check-inline">
                                <input class="form-check-input" type="radio" id="attendingNo" name="attendance"
                                    v-model="isAttending" value="no" />
                                <label class="form-check-label" for="attendingNo">{{ options2 }}</label>
                            </div>
                        </div>
                        <span class="text-danger" v-if="errorMessage">{{ errorMessage }}</span>
                    </div>
                </fieldset>
                <fieldset>
                    <!-- <legend>{{ datos }}</legend> -->
                    <div class="form-group mb-3">
                        <label for="nombre" class="form-label">{{ inputName }}</label>
                        <input type="text" class="form-control input_text" id="nombre" v-model="nombre"
                            placeholder="Ej: Juan Pérez" />
                    </div>
                    <div class="form-group mb-3">
                        <label for="informacionAdicional" class="form-label">{{ inputTxtArea }}</label>
                        <textarea class="form-control input_text" id="informacionAdicional" v-model="informacionAdicional"
                            rows="1" placeholder="Ej: Vegetariano, alergico, etc."></textarea>
                    </div>
                </fieldset>
    
            </div>
        </div>
        <div class="btnForm">
            <p class="text_limite">{{ limite }}</p>
            <Boton v-if="!isFormIncomplete" label="ENVIAR" customClass="btn-mayor" @click="enviarAWhatsApp"/>
        </div>
    </div>
</template>
<style>
.containerFormulario {
    width: 100%;
    height:400px;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin:2rem 0;
}

.content_title_formulario {
    display: flex;
    justify-content: center;
    align-items: center;
}
.titleFormulario,
legend{
    font-family:var(--body-font);
    color:var(--title-color);
    font-weight: var(--font-bold);
}
input#attendingYes.form-check-input,
input#attendingNo.form-check-input{
    border:1px solid var(--first-text-color);
}
.titleFormulario{
    font-size: 1.2rem;
}
legend{
    font-size: .8rem;
    line-height: 80%;
    text-align: center;
}
.-flex{
    display: flex;
    justify-content: center;
}
.modal-body {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    
}

.content__radio {
    display: flex;
    justify-content:center;
    align-items: center;
    font-size: 1rem;
    font-family: var(--body-font);
    font-weight: var(--font-bold);
    color:var(--first-text-color);
    width:100%;
}
.text_limite{
    font-size: .75rem;
    font-family: var(--body-font);
    font-weight: var(--font-light);
    text-align: center;
    color:var(--first-text-color);
    line-height: 0%;
}

.form-check-input {
    border: 2px solid var(--line-color-dark);
}

.form-control {
    border: none;
    border-radius: 0%;
    width: 100%;
}

.input_text {
    border-bottom: 1px solid var(--title-color);
}
input,
textarea,
.form-label {
    font-size: 1rem;
    font-family: var(--body-font);
    font-weight: var(--font-light);
    color:var(--first-text-color);
}
.form-label{
    line-height: 0%;
}

.form-control::placeholder{
    color: var(--second-text-color);
    font-size:.8rem;
}
@media (min-width: 768px) and (max-width: 991px) {
    .containerFormulario {
        width:900px;
        height:800px;
    }

    .titleFormulario{
        font-size: 2.5rem;
    }
    legend{
        font-size: 1.6rem;
    }
    .modal-body {
        width: 100%;
    }
    .content__radio {
        font-size: 1.5rem;
        width:450px;
    }
    input,
    textarea,
    .form-label,
    ::placeholder {
        font-size: 1.5rem;
    }
}
@media (min-width: 1025px) {
    .containerFormulario {
        width:900px;
        height:900px;
    }

    .titleFormulario{
        font-size: 3.5rem;
    }
    legend{
        font-size: 2.6rem;
        margin-bottom:2rem;
    }
    .modal-body {
        width:800px;
    }
    .content__radio {
        font-size: 2rem;
        width:550px;
    }
    .form-group,
    .mb-3{
        margin-top: 4rem;
        
    }
    .text_limite{
        font-size: 1rem;
    }
    input,
    textarea,
    .form-label,
    ::placeholder {
        font-size: 2rem;
    }
}
</style>