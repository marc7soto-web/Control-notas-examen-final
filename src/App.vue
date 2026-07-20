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

            <input id="nota1" type="number" placeholder="Ingrese Nota 1">

          </div>

          <div class="form-group">

            <label for="nota2">
              Nota 2
            </label>

            <input id="nota2" type="number" placeholder="Ingrese Nota 2">

          </div>

          <div class="form-group">

            <label for="nota3">
              Nota 3
            </label>

            <input id="nota3" type="number" placeholder="Ingrese Nota 3">

          </div>

          <div class="form-group">

            <label for="asistencia">
              Asistencia (%)
            </label>

            <input id="asistencia" type="number" placeholder="Ingrese asistencia">

          </div>

          <button type="button" class="calculate-button">
            Calcular
          </button>

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

// Controla la pestaña actualmente seleccionada.
const activeTab = ref('calificaciones')
</script>