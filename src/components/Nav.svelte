<script>
  let isOpen = false;
  export let segment;
  function toggleNav() {
    isOpen = !isOpen;
  }
</script>

<style>
  @media (min-width: 769px) {
    nav {
      border-bottom: 1px solid gray;
    }
    a.navbar-item.is-active {
      font-weight: 700;
    }
  }
</style>

<nav class="navbar" role="navigation" aria-label="main navigation">
  <div class="navbar-brand">
    <a href="/" class="navbar-item">
      <img src="logo.png" alt="virusLogo" />
    </a>
    <span
      class="navbar-burger"
      aria-label="menu"
      aria-expanded="false"
      class:is-active={isOpen}
      on:click={toggleNav}>
      <span aria-hidden="true" />
      <span aria-hidden="true" />
      <span aria-hidden="true" />
    </span>
  </div>
  <div class="navbar-menu" class:is-active={isOpen}>
    <div class="navbar-start">
      <a href="/" class="navbar-item" class:is-active={segment === undefined}>
        HOME
      </a>
      <a
        href="/about"
        class="navbar-item"
        class:is-active={segment === 'about'}>
        ABOUT
      </a>
    </div>
  </div>
</nav>
