<script>
  import Dropdown from '../dropdown/Dropdown.svelte';
  import './navbar.style.css';

  let isDropdownOpen = false;

  function toggleDropdown() {
    isDropdownOpen = !isDropdownOpen;
  }

  function closeDropdown() {
    isDropdownOpen = false;
  }
</script>

<header>
  <nav>
    <div>
      <img src="/assets/logobarber.png" alt="logo-barberia" />
    </div>

    <div class="container-buttons">
      <ul class="bebas-neue-regular">
        <li><a href="#home">Inicio</a></li>
        <li><a href="#service">Servicios</a></li>
        <li><a href="#gallery">Galería</a></li>
        <li><a href="#location">Ubicación</a></li>
      </ul>

      <button type="button" class="bebas-neue-regular btn-cta">
        Reservar Turno
      </button>

      <button
        type="button"
        aria-label="Abrir menú"
        class="btn-hamburger"
        on:click={toggleDropdown}
      >
        <img src="/assets/icons/icon-hamburguer.svg" alt="icono menú" />
      </button>
    </div>
  </nav>

  <Dropdown visible={isDropdownOpen} onClose={closeDropdown} />
</header>
