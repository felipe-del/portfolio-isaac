<script setup>
useHead({
  title: 'Blog',
  meta: [
    {
      name: 'description',
      content: 'Artículos de Isaac Brenes sobre desarrollo Full Stack, estructuras de datos, TypeScript y proyectos de ingeniería de software.'
    }
  ]
})

const posts = [
  {
    titulo: 'Estructuras de Datos en C++',
    categoria: 'C++',
    fecha: '13 ene. 2026',
    resumen: 'Repaso práctico de las estructuras de datos fundamentales y su implementación en C++, pensado como material de estudio y referencia rápida.'
  },
  {
    titulo: 'Aprenda a vivir sin un mapa',
    categoria: 'Reflexión personal',
    fecha: '25 may. 2025',
    resumen: 'Una reflexión sobre el proceso de aprender ingeniería de software sin una ruta fija, y cómo la incertidumbre también enseña.'
  },
  {
    titulo: 'ProStep – Plataforma Inteligente de Vinculación Laboral',
    categoria: 'Proyecto académico Full Stack',
    fecha: '23 abr. 2025',
    resumen: 'Bitácora de construcción de ProStep, una plataforma para conectar estudiantes con oportunidades de práctica profesional.'
  },
  {
    titulo: 'DevTree – Social Links Hub',
    categoria: 'Full Stack Project',
    fecha: '23 abr. 2025',
    resumen: 'Cómo construí un hub de enlaces sociales con autenticación, edición de perfil en tiempo real y panel de administración.'
  },
  {
    titulo: 'CashTrackr – Personal Finance & Budget Management',
    categoria: 'Full Stack Project',
    fecha: '22 abr. 2025',
    resumen: 'Notas de desarrollo de una plataforma de finanzas personales con presupuestos por categoría y notificaciones automáticas.'
  },
  {
    titulo: 'POS – Point of Sale System',
    categoria: 'Full Stack Project',
    fecha: '21 abr. 2025',
    resumen: 'Diseño e implementación de un sistema de punto de venta para pequeños negocios, con control de inventario y reportes.'
  },
  {
    titulo: 'TypeScript Complete Guide – From Basics to Advanced',
    categoria: 'TypeScript',
    fecha: '17 mar. 2025',
    resumen: 'Guía completa de TypeScript, desde tipos básicos hasta patrones avanzados usados en proyectos reales.'
  },
  {
    titulo: 'Los Cuatro Pilares de la Programación Orientada a Objetos (POO)',
    categoria: 'Software Engineering',
    fecha: '11 ene. 2025',
    resumen: 'Explicación de encapsulamiento, abstracción, herencia y polimorfismo con ejemplos aplicados a proyectos propios.'
  },
  {
    titulo: 'IMPACT – Integrated Management Platform and Control Tracker',
    categoria: 'Academic Information Systems Project',
    fecha: '9 may. 2024',
    resumen: 'Documentación del desarrollo de IMPACT, una plataforma institucional de gestión y control con trazabilidad por rol.'
  }
]
</script>

<template>
  <section class="intro">
    <div class="container">
      <p class="tag">// blog.vue</p>
      <h1>Blog</h1>
      <p class="lead muted">
        Notas sobre desarrollo Full Stack, estructuras de datos y el proceso
        detrás de mis proyectos.
      </p>
    </div>
  </section>

  <section class="section">
    <div class="container">
      <ul class="post-list">
        <li v-for="post in posts" :key="post.titulo" class="card post-item">
          <div class="post-meta mono small">
            <span class="accent">{{ post.categoria }}</span>
            <span class="muted">{{ post.fecha }}</span>
          </div>
          <h2>{{ post.titulo }}</h2>
          <p class="muted">{{ post.resumen }}</p>
        </li>
      </ul>
    </div>
  </section>
</template>

<style scoped>
.intro {
  padding: 72px 0 48px;
  border-bottom: 1px solid var(--border);
}

.lead {
  max-width: 640px;
  font-size: 17px;
  margin-top: 16px;
}

.section {
  padding: 56px 0;
}

.post-list {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.post-item h2 {
  font-size: 17px;
  margin: 6px 0 8px;
}

.post-meta {
  display: flex;
  gap: 14px;
  flex-wrap: wrap;
}

.small {
  font-size: 12.5px;
}

.accent {
  color: var(--accent);
}
</style>
