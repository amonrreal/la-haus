<template>
  <nav class="navbar navbar-expand-lg bg-white border-b border-gray-2">
    <div class="container">
      <button
        class="navbar-toggler border-none relative"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <img src="../assets/menu-icon.svg" alt="Menu" />
        <span
          class="rounded-lg absolute bg-lightGreen w-3 h-3 top-0 right-1"
        ></span>
      </button>
      <router-link
        :to="{ name: 'Home' }"
        class="navbar-brand block lg:hidden ml-2"
      >
        <img src="../assets/icon.svg" alt="La Haus" />
      </router-link>
      <router-link :to="{ name: 'Home' }" class="navbar-brand hidden lg:block">
        <img src="../assets/logo.svg" alt="La Haus" />
      </router-link>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <a
              class="nav-link text-darkGreen hover:text-darkGreen focus:text-darkGreen"
              aria-current="page"
              href="#"
            >
              Cundinamarca
            </a>
          </li>
          <li class="nav-item ml-4">
            <a
              class="nav-link text-darkGreen hover:text-darkGreen focus:text-darkGreen"
              href="#"
            >
              Antioquia
            </a>
          </li>
          <li class="nav-item ml-4">
            <a
              class="nav-link text-darkGreen hover:text-darkGreen focus:text-darkGreen"
              href="#"
            >
              Recursos
            </a>
          </li>
          <li class="nav-item ml-4">
            <a
              class="nav-link relative font-bold text-darkGreen hover:text-darkGreen focus:text-darkGreen"
              href="#"
            >
              Mi Perfil
              <fa icon="chevron-down" class="font-normal ml-1" />
              <span
                class="rounded-lg absolute bg-lightGreen w-3 h-3 -mt-1"
              ></span>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Nav',
}
</script>

<style lang="scss">
.navbar {
  .container {
    justify-content: start !important;
    .navbar-toggler:focus {
      box-shadow: inherit !important;
    }
  }
}
</style>
