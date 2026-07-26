<script setup>
useHead({
  title: 'Inicio',
  meta: [
    {
      name: 'description',
      content: 'Isaac Brenes, Ingeniero en Sistemas de Información y Desarrollador Full Stack. Portafolio con proyectos, experiencia y blog técnico.'
    }
  ]
})

const stack = [
  { label: 'Backend', items: ['Java', 'Spring Boot', 'Node.js', 'NestJS'] },
  { label: 'Frontend', items: ['React', 'Next.js', 'TypeScript'] },
  { label: 'Datos e infraestructura', items: ['PostgreSQL', 'Apache Kafka', 'Keycloak', 'Docker'] }
]
</script>

<template>
  <section class="hero">
    <div class="container hero-inner">
      <p class="tag">// disponible para nuevos proyectos</p>
      <h1 class="hero-title">
        Isaac Brenes<br />
        <span class="accent">Ingeniero de Sistemas &amp; Desarrollador Full Stack</span>
      </h1>
      <p class="hero-lead">
        Construyo aplicaciones web escalables de punta a punta: desde APIs con
        Spring Boot y arquitecturas de microservicios, hasta interfaces
        modernas con React y TypeScript. Me interesa el rendimiento, la
        seguridad y la experiencia de quien usa el sistema todos los días.
      </p>
      <div class="hero-actions">
        <NuxtLink to="/proyectos" class="btn btn-solid">Ver proyectos</NuxtLink>
        <NuxtLink to="/contacto" class="btn">Hablemos</NuxtLink>
      </div>
    </div>
  </section>

  <section class="section">
    <div class="container">
      <h2 class="section-title">01 · En qué trabajo actualmente</h2>
      <div class="grid">
        <div class="card">
          <p class="mono accent small">Universidad Nacional de Costa Rica</p>
          <h3>Sistema de Inventarios por Microservicios</h3>
          <p class="muted">
            Backend con Spring Boot y comunicación asíncrona vía Apache Kafka,
            autenticación centralizada con Keycloak (RBAC) y frontend en React
            + TypeScript bajo una arquitectura modular.
          </p>
        </div>
        <div class="card">
          <p class="mono accent small">SOIN Soluciones Integrales S.A.</p>
          <h3>Implementación de Software Empresarial</h3>
          <p class="muted">
            Configuración y validación de plataformas según requerimientos
            funcionales, análisis de incidencias y mejora continua de procesos
            operativos en entornos de implementación real.
          </p>
        </div>
      </div>
    </div>
  </section>

  <section class="section">
    <div class="container">
      <h2 class="section-title">02 · Con qué construyo</h2>
      <div class="stack-grid">
        <div v-for="group in stack" :key="group.label" class="card stack-card">
          <p class="mono small muted">{{ group.label }}</p>
          <div class="stack-tags">
            <span v-for="item in group.items" :key="item" class="tag">{{ item }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="section cta-section">
    <div class="container cta-inner">
      <div>
        <h2 class="section-title">¿Buscas a alguien para tu equipo?</h2>
        <p class="muted">
          Escríbeme y conversemos sobre tu proyecto o vacante.
        </p>
      </div>
      <NuxtLink to="/contacto" class="btn btn-solid">Ir a contacto</NuxtLink>
    </div>
  </section>
</template>

<style scoped>
.hero {
  padding: 96px 0 72px;
  border-bottom: 1px solid var(--border);
}

.hero-inner {
  max-width: 720px;
}

.hero-title {
  font-size: clamp(28px, 4vw, 42px);
  margin-bottom: 20px;
}

.hero-title .accent {
  color: var(--accent);
  font-size: clamp(18px, 2.4vw, 24px);
  display: inline-block;
  margin-top: 8px;
}

.hero-lead {
  color: var(--text-muted);
  font-size: 17px;
  max-width: 620px;
}

.hero-actions {
  display: flex;
  gap: 14px;
  margin-top: 28px;
  flex-wrap: wrap;
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
  margin-bottom: 24px;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
}

.grid h3 {
  font-size: 17px;
  margin: 8px 0 10px;
}

.small {
  font-size: 12.5px;
}

.accent {
  color: var(--accent);
}

.stack-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 20px;
}

.stack-card p {
  margin-bottom: 12px;
}

.stack-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.cta-section {
  border-bottom: none;
}

.cta-inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;
  flex-wrap: wrap;
}

.cta-inner .section-title {
  text-transform: none;
  color: var(--text);
  font-size: 22px;
  margin-bottom: 6px;
}
</style>
