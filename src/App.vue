<template>
  <div class="app">

    <!-- Encabezado principal -->
    <header class="navbar">

      <h1 class="title">
        Programación Front End - IPLACEX 2026
      </h1>

      <hr class="divider">

      <div class="navigation-bar">

        <!-- Pestañas del sistema -->
        <div class="tabs">

          <button class="tab-button" :class="{ active: activeTab === 'calificaciones' }"
            @click="activeTab = 'calificaciones'">
            Cálculo de calificaciones
          </button>

          <button class="tab-button" :class="{ active: activeTab === 'registro' }" @click="activeTab = 'registro'">
            Formulario de Registro
          </button>

        </div>

        <!-- Área de búsqueda -->
        <div class="search-area">

          <input type="text" class="search-input" placeholder="Ingrese texto para búsqueda">

          <button class="search-button">
            Búsqueda
          </button>

        </div>

      </div>

    </header>

    <main class="content">

      <section v-if="activeTab === 'calificaciones'">

        <h2 class="section-title">
          Cálculo de calificaciones
        </h2>

        <form class="grades-form">

          <div class="form-group">

            <label for="nota1">
              Nota 1
            </label>

            <input id="nota1" type="number" v-model="nota1" placeholder="Ingrese Nota 1">

            <small v-if="nota1 && (nota1 < 10 || nota1 > 70)" class="error-message">
              Debe ingresar una nota entre 10 y 70.
            </small>
          </div>

          <div class="form-group">

            <label for="nota2">
              Nota 2
            </label>

            <input id="nota2" type="number" v-model="nota2" placeholder="Ingrese Nota 2">

            <small v-if="nota2 && (nota2 < 10 || nota2 > 70)" class="error-message">
              Debe ingresar una nota entre 10 y 70.
            </small>
          </div>

          <div class="form-group">

            <label for="nota3">
              Nota 3
            </label>

            <input id="nota3" type="number" v-model="nota3" placeholder="Ingrese Nota 3">

            <small v-if="nota3 && (nota3 < 10 || nota3 > 70)" class="error-message">
              Debe ingresar una nota entre 10 y 70.
            </small>
          </div>

          <div class="form-group">

            <label for="asistencia">
              Asistencia (%)
            </label>

            <input id="asistencia" type="number" v-model="asistencia" placeholder="Ingrese asistencia">

            <small v-if="asistencia && (asistencia < 0 || asistencia > 100)" class="error-message">
              La asistencia debe estar entre 0 y 100.
            </small>
          </div>

          <button type="button" class="calculate-button" @click="calcularPromedio">
            Calcular
          </button>

          <div v-if="promedioFinal" class="result-card">

            <h3>
              Resultado Final
            </h3>

            <p>
              Promedio: {{ promedioFinal }}
            </p>

            <p :class="resultado === 'APROBADO'
              ? 'approved'
              : 'failed'">
              {{ resultado }}
            </p>

          </div>

        </form>

      </section>
      <section v-if="activeTab === 'registro'">

        <h2>Formulario de Registro</h2>

        <p>
          Formulario en construcción.
        </p>

      </section>

    </main>

  </div>
</template>

<script setup>

import { ref } from 'vue'

// Controla la pestaña seleccionada.
const activeTab = ref('calificaciones')

// Datos del formulario.
const nota1 = ref('')
const nota2 = ref('')
const nota3 = ref('')
const asistencia = ref('')

// Resultado final del cálculo.
const promedioFinal = ref(null)
const resultado = ref('')

// Calcula el promedio ponderado.
const calcularPromedio = () => {

  const promedio =
    (Number(nota1.value) * 0.35) +
    (Number(nota2.value) * 0.35) +
    (Number(nota3.value) * 0.30)

  promedioFinal.value = promedio.toFixed(2)

  if (promedio >= 40 && Number(asistencia.value) >= 80) {
    resultado.value = 'APROBADO'
  } else {
    resultado.value = 'REPROBADO'
  }

}

</script>