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

        <h2>Cálculo de calificaciones</h2>

        <p>
          Formulario en construcción.
        </p>

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