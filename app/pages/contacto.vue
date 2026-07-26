<script setup>
useHead({
  title: 'Contacto',
  meta: [
    {
      name: 'description',
      content: 'Contacta a Isaac Brenes para propuestas de proyectos, colaboraciones o vacantes como desarrollador Full Stack.'
    }
  ]
})

const nombre = ref('')
const email = ref('')
const mensaje = ref('')
const enviado = ref(false)

const canales = [
  { label: 'Correo', valor: 'contacto@isaacbrenes.dev', href: 'mailto:contacto@isaacbrenes.dev' },
  { label: 'GitHub', valor: 'github.com/felipe-del', href: 'https://github.com/felipe-del' },
  { label: 'Ubicación', valor: 'San José, Costa Rica', href: null }
]

function enviarMensaje() {
  const asunto = encodeURIComponent(`Contacto desde el portafolio - ${nombre.value}`)
  const cuerpo = encodeURIComponent(`${mensaje.value}\n\n— ${nombre.value} (${email.value})`)
  window.location.href = `mailto:contacto@isaacbrenes.dev?subject=${asunto}&body=${cuerpo}`
  enviado.value = true
}
</script>

<template>
  <section class="intro">
    <div class="container">
      <p class="tag">// contacto.vue</p>
      <h1>Contacto</h1>
      <p class="lead muted">
        ¿Tienes un proyecto, una vacante o una idea? Escríbeme y con gusto
        conversamos.
      </p>
    </div>
  </section>

  <section class="section">
    <div class="container two-col">
      <form class="card form" @submit.prevent="enviarMensaje">
        <label class="field">
          <span class="mono small muted">Nombre</span>
          <input v-model="nombre" type="text" name="nombre" required placeholder="Tu nombre" />
        </label>
        <label class="field">
          <span class="mono small muted">Correo</span>
          <input v-model="email" type="email" name="email" required placeholder="tu@correo.com" />
        </label>
        <label class="field">
          <span class="mono small muted">Mensaje</span>
          <textarea v-model="mensaje" name="mensaje" rows="5" required placeholder="Cuéntame sobre tu proyecto"></textarea>
        </label>
        <button type="submit" class="btn btn-solid">Enviar mensaje</button>
        <p v-if="enviado" class="sent-note mono small accent">
          Abriendo tu cliente de correo…
        </p>
      </form>

      <div class="channels">
        <h2 class="section-title">Otros canales</h2>
        <div class="card">
          <ul class="channel-list">
            <li v-for="c in canales" :key="c.label">
              <span class="mono small muted">{{ c.label }}</span>
              <a v-if="c.href" :href="c.href" target="_blank" rel="noopener">{{ c.valor }}</a>
              <span v-else>{{ c.valor }}</span>
            </li>
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
  max-width: 560px;
  font-size: 17px;
  margin-top: 16px;
}

.section {
  padding: 56px 0;
}

.two-col {
  display: grid;
  grid-template-columns: 1.3fr 1fr;
  gap: 40px;
  align-items: start;
}

.form {
  display: flex;
  flex-direction: column;
  gap: 18px;
}

.field {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

input, textarea {
  background: var(--bg);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 10px 12px;
  color: var(--text);
  font-family: var(--font-body);
  font-size: 14.5px;
  resize: vertical;
}

input::placeholder, textarea::placeholder {
  color: var(--text-muted);
}

.sent-note {
  margin: 0;
}

.section-title {
  font-size: 15px;
  letter-spacing: 0.02em;
  color: var(--text-muted);
  text-transform: uppercase;
  margin-bottom: 20px;
}

.channel-list {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.channel-list li {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.small {
  font-size: 12.5px;
}

@media (max-width: 760px) {
  .two-col {
    grid-template-columns: 1fr;
  }
}
</style>
