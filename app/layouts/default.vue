<script setup>
const route = useRoute()

const tabs = [
  { name: 'inicio.vue', to: '/', label: 'Inicio' },
  { name: 'sobre-mi.vue', to: '/sobre-mi', label: 'Sobre Mí' },
  { name: 'proyectos.vue', to: '/proyectos', label: 'Proyectos' },
  { name: 'blog.vue', to: '/blog', label: 'Blog' },
  { name: 'contacto.vue', to: '/contacto', label: 'Contacto' }
]

const isActive = (to) => route.path === to
</script>

<template>
  <div class="shell">
    <header class="topbar">
      <div class="container topbar-inner">
        <NuxtLink to="/" class="brand">
          <span class="brand-dot" aria-hidden="true"></span>
          isaac<span class="muted">.dev</span>
        </NuxtLink>

        <nav class="tabs" aria-label="Navegación principal">
          <NuxtLink
            v-for="tab in tabs"
            :key="tab.to"
            :to="tab.to"
            class="tab"
            :class="{ 'tab-active': isActive(tab.to) }"
          >
            <span class="tab-dot" :class="{ 'tab-dot-active': isActive(tab.to) }" aria-hidden="true"></span>
            {{ tab.name }}
          </NuxtLink>
        </nav>
      </div>
    </header>

    <main class="content">
      <slot />
    </main>

    <footer class="statusbar">
      <div class="container statusbar-inner">
        <div class="status-left">
          <span class="status-item">
            <span class="dot-online" aria-hidden="true"></span>
            disponible para nuevos proyectos
          </span>
          <span class="status-item muted">San José, Costa Rica</span>
        </div>
        <div class="status-right">
          <a href="mailto:contacto@isaacbrenes.dev" class="status-item">contacto@isaacbrenes.dev</a>
          <a href="https://github.com/felipe-del" target="_blank" rel="noopener" class="status-item">github/felipe-del</a>
          <span class="status-item muted">© {{ new Date().getFullYear() }}</span>
        </div>
      </div>
    </footer>
  </div>
</template>

<style scoped>
.shell {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  position: relative;
  z-index: 1;
}

.topbar {
  border-bottom: 1px solid var(--border);
  background: var(--bg-panel);
  position: sticky;
  top: 0;
  z-index: 10;
}

.topbar-inner {
  display: flex;
  align-items: center;
  gap: 32px;
  padding-top: 14px;
  padding-bottom: 14px;
  flex-wrap: wrap;
}

.brand {
  font-family: var(--font-display);
  font-weight: 800;
  font-size: 17px;
  color: var(--text);
  display: flex;
  align-items: center;
  gap: 8px;
  text-decoration: none;
}

.brand:hover {
  text-decoration: none;
}

.brand-dot {
  width: 9px;
  height: 9px;
  border-radius: 50%;
  background: var(--accent);
  display: inline-block;
}

.tabs {
  display: flex;
  gap: 2px;
  flex-wrap: wrap;
  overflow-x: auto;
}

.tab {
  font-family: var(--font-display);
  font-size: 13px;
  color: var(--text-muted);
  padding: 8px 14px;
  border-radius: var(--radius) var(--radius) 0 0;
  border: 1px solid transparent;
  display: inline-flex;
  align-items: center;
  gap: 8px;
  white-space: nowrap;
  text-decoration: none;
}

.tab:hover {
  color: var(--text);
  text-decoration: none;
  background: var(--bg-panel-2);
}

.tab-active {
  color: var(--accent);
  background: var(--bg);
  border-color: var(--border);
  border-bottom-color: var(--bg);
}

.tab-dot {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: var(--border);
}

.tab-dot-active {
  background: var(--accent);
}

.content {
  flex: 1;
}

.statusbar {
  border-top: 1px solid var(--border);
  background: var(--bg-panel);
  font-family: var(--font-display);
  font-size: 12.5px;
}

.statusbar-inner {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 16px;
  padding-top: 10px;
  padding-bottom: 10px;
  flex-wrap: wrap;
  color: var(--text-muted);
}

.status-left, .status-right {
  display: flex;
  align-items: center;
  gap: 18px;
  flex-wrap: wrap;
}

.status-item {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  color: var(--text-muted);
  text-decoration: none;
}

.status-item:hover {
  color: var(--accent);
  text-decoration: none;
}

.dot-online {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: var(--accent-green);
  box-shadow: 0 0 0 3px rgba(126, 226, 184, 0.15);
}
</style>
