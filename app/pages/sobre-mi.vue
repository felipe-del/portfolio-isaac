<script setup>
useHead({
  title: 'Sobre Mí',
  meta: [
    {
      name: 'description',
      content: 'Trayectoria de Isaac Brenes: experiencia laboral, formación académica y certificaciones como desarrollador Full Stack.'
    }
  ]
})

const experiencia = [
  {
    periodo: 'May 2026 – Actualidad',
    empresa: 'SOIN Soluciones Integrales S.A.',
    rol: 'TAPP Expert · Implementación de Software',
    detalle: 'Implementación y soporte de soluciones empresariales, configuración de plataformas según requerimientos funcionales y seguimiento de incidencias en entornos de implementación.'
  },
  {
    periodo: 'Abr 2026 – Actualidad',
    empresa: 'Universidad Nacional de Costa Rica',
    rol: 'Desarrollador Full Stack · Sistema Programa Servicios Generales',
    detalle: 'Diseño de un sistema de inventarios basado en microservicios: backend con Spring Boot y Apache Kafka, autenticación con Keycloak (RBAC) y frontend en React + TypeScript.'
  },
  {
    periodo: 'Ene 2026 – May 2026',
    empresa: 'Clocky App Ltd (Reino Unido)',
    rol: 'Ingeniero de Software Junior (Remoto)',
    detalle: 'Desarrollo backend en Java, PHP y JavaScript sobre Google Cloud Platform (App Engine, Cloud Functions, Pub/Sub), aplicando arquitectura modular y prácticas de seguridad Zero Trust.'
  },
  {
    periodo: 'Jun 2025 – Nov 2025',
    empresa: 'TicoDevs Software Solutions',
    rol: 'Desarrollador Backend (Remoto)',
    detalle: 'APIs REST con Java y Spring Boot, modelado de datos con JPA/Hibernate y lógica de negocio escalable, trabajando bajo metodología Scrum.'
  },
  {
    periodo: 'Feb 2024 – May 2025',
    empresa: 'CIMPA - Universidad de Costa Rica',
    rol: 'Desarrollador Junior',
    detalle: 'Sistema web para gestión de inventarios y activos, automatizando procesos manuales de control y préstamos con flujos por roles y trazabilidad.'
  },
  {
    periodo: 'Oct 2023 – Nov 2025',
    empresa: 'Universidad Nacional (UNA)',
    rol: 'Asistente de Docencia en Programación',
    detalle: 'Apoyo académico en cursos de Java y Programación Orientada a Objetos: revisión de tareas, asesoría en depuración de código y buenas prácticas.'
  }
]

const formacion = [
  {
    titulo: 'Licenciatura en Informática con énfasis en Sistemas Web',
    institucion: 'Universidad Nacional de Costa Rica',
    periodo: 'En curso (inicio 2026 – 2027)'
  },
  {
    titulo: 'Bachillerato en Ingeniería en Sistemas de Información',
    institucion: 'Universidad Nacional de Costa Rica',
    periodo: '2022 – 2025'
  },
  {
    titulo: 'Diplomado en Aplicaciones Informáticas',
    institucion: 'Universidad Nacional de Costa Rica (salida lateral)',
    periodo: '2024'
  },
  {
    titulo: 'Bachillerato en Educación Media',
    institucion: 'Colegio San Luis Gonzaga',
    periodo: '2021'
  }
]

const certificaciones = [
  'Full Stack Development — Udemy',
  'Microservices with Node.js and React — Udemy',
  'Scrum Fundamentals Certified — SCRUMstudy',
  'Oracle Java Foundations — Oracle'
]
</script>

<template>
  <section class="intro">
    <div class="container">
      <p class="tag">// sobre-mi.vue</p>
      <h1>Sobre mí</h1>
      <p class="lead muted">
        Soy Isaac Brenes, Ingeniero en Sistemas de Información enfocado en la
        construcción de aplicaciones web completas, desde el frontend hasta
        el backend, con énfasis en rendimiento, escalabilidad y experiencia
        de usuario. He participado en sistemas empresariales, APIs y
        plataformas web, cubriendo análisis, diseño, implementación e
        integración. Me adapto con facilidad a nuevas tecnologías y trabajo
        cómodo bajo metodologías ágiles, siempre orientado a resolver
        necesidades reales de negocio.
      </p>
    </div>
  </section>

  <section class="section">
    <div class="container">
      <h2 class="section-title">Experiencia laboral</h2>
      <ol class="timeline">
        <li v-for="(item, i) in experiencia" :key="item.empresa" class="timeline-item">
          <span class="line-no mono">{{ String(i + 1).padStart(2, '0') }}</span>
          <div class="timeline-content">
            <p class="mono small accent">{{ item.periodo }}</p>
            <h3>{{ item.empresa }}</h3>
            <p class="rol muted">{{ item.rol }}</p>
            <p class="muted">{{ item.detalle }}</p>
          </div>
        </li>
      </ol>
    </div>
  </section>

  <section class="section">
    <div class="container two-col">
      <div>
        <h2 class="section-title">Formación académica</h2>
        <div class="list">
          <div v-for="f in formacion" :key="f.titulo" class="card list-item">
            <h3>{{ f.titulo }}</h3>
            <p class="muted">{{ f.institucion }}</p>
            <p class="mono small accent">{{ f.periodo }}</p>
          </div>
        </div>
      </div>
      <div>
        <h2 class="section-title">Certificaciones</h2>
        <div class="card">
          <ul class="cert-list">
            <li v-for="c in certificaciones" :key="c">{{ c }}</li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.intro {
  padding: 72px 0 48px;
  border-bottom: 1px solid var(--border);
}

.lead {
  max-width: 680px;
  font-size: 17px;
  margin-top: 16px;
}

.section {
  padding: 56px 0;
  border-bottom: 1px solid var(--border);
}

.section-title {
  font-size: 15px;
  letter-spacing: 0.02em;
  color: var(--text-muted);
  text-transform: uppercase;
  margin-bottom: 28px;
}

.timeline {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 0;
}

.timeline-item {
  display: grid;
  grid-template-columns: 44px 1fr;
  gap: 16px;
  padding: 20px 0;
  border-top: 1px solid var(--border);
}

.timeline-item:last-child {
  border-bottom: 1px solid var(--border);
}

.line-no {
  color: var(--text-muted);
  font-size: 13px;
  padding-top: 2px;
}

.timeline-content h3 {
  font-size: 16px;
  margin: 4px 0 4px;
}

.rol {
  font-size: 14px;
  margin-bottom: 8px;
}

.small {
  font-size: 12.5px;
}

.accent {
  color: var(--accent);
}

.two-col {
  display: grid;
  grid-template-columns: 1.3fr 1fr;
  gap: 40px;
}

.list {
  display: flex;
  flex-direction: column;
  gap: 14px;
}

.list-item h3 {
  font-size: 15px;
  margin-bottom: 4px;
}

.cert-list {
  margin: 0;
  padding-left: 18px;
  color: var(--text-muted);
  display: flex;
  flex-direction: column;
  gap: 10px;
}

@media (max-width: 760px) {
  .two-col {
    grid-template-columns: 1fr;
  }
}
</style>
