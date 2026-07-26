<script setup>
useHead({
  title: 'Proyectos',
  meta: [
    {
      name: 'description',
      content: 'Proyectos Full Stack de Isaac Brenes: DevTree, CashTrackr, POS, ProStep e IMPACT, construidos con Java, Spring Boot, React y TypeScript.'
    }
  ]
})

const proyectos = [
  {
    nombre: 'DevTree',
    tipo: 'Proyecto Full Stack',
    descripcion: 'Hub de enlaces sociales al estilo Linktree, con autenticación de usuarios, edición de perfil en tiempo real y panel de administración de enlaces.',
    tecnologias: ['React', 'TypeScript', 'Node.js', 'MongoDB'],
    link: 'https://github.com/felipe-del'
  },
  {
    nombre: 'CashTrackr',
    tipo: 'Finanzas personales',
    descripcion: 'Plataforma de gestión de presupuestos y finanzas personales: registro de gastos, presupuestos por categoría y notificaciones por correo.',
    tecnologias: ['React', 'TypeScript', 'Node.js', 'PostgreSQL'],
    link: 'https://github.com/felipe-del'
  },
  {
    nombre: 'POS · Point of Sale',
    tipo: 'Gestión empresarial',
    descripcion: 'Sistema de punto de venta orientado a pequeños negocios: control de inventario, ventas y reportes de facturación.',
    tecnologias: ['React', 'Node.js', 'SQL'],
    link: 'https://github.com/felipe-del'
  },
  {
    nombre: 'ProStep',
    tipo: 'Proyecto académico Full Stack',
    descripcion: 'Plataforma inteligente de vinculación laboral pensada para conectar estudiantes con oportunidades de práctica profesional.',
    tecnologias: ['React', 'Spring Boot', 'PostgreSQL'],
    link: 'https://github.com/felipe-del'
  },
  {
    nombre: 'IMPACT',
    tipo: 'Sistemas de información académico',
    descripcion: 'Plataforma integrada de gestión y control para seguimiento de procesos institucionales, con reportes y trazabilidad por rol.',
    tecnologias: ['Java', 'Spring Boot', 'MySQL'],
    link: 'https://github.com/felipe-del'
  }
]
</script>

<template>
  <section class="intro">
    <div class="container">
      <p class="tag">// proyectos.vue</p>
      <h1>Proyectos</h1>
      <p class="lead muted">
        Aplicaciones Full Stack construidas con ecosistemas modernos de
        JavaScript, TypeScript y Java, enfocadas en productividad, finanzas
        y gestión institucional.
      </p>
    </div>
  </section>

  <section class="section">
    <div class="container">
      <div class="projects-grid">
        <article v-for="p in proyectos" :key="p.nombre" class="card project-card">
          <div class="project-head">
            <h2>{{ p.nombre }}</h2>
            <span class="mono small accent">{{ p.tipo }}</span>
          </div>
          <p class="muted">{{ p.descripcion }}</p>
          <div class="tags">
            <span v-for="t in p.tecnologias" :key="t" class="tag">{{ t }}</span>
          </div>
          <a :href="p.link" target="_blank" rel="noopener" class="btn project-link">Ver en GitHub</a>
        </article>
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
  max-width: 640px;
  font-size: 17px;
  margin-top: 16px;
}

.section {
  padding: 56px 0;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}

.project-card {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.project-head {
  display: flex;
  align-items: baseline;
  justify-content: space-between;
  gap: 12px;
  flex-wrap: wrap;
}

.project-head h2 {
  font-size: 18px;
  margin: 0;
}

.small {
  font-size: 12px;
}

.accent {
  color: var(--accent);
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin: 4px 0 8px;
}

.project-link {
  align-self: flex-start;
  margin-top: auto;
}
</style>
