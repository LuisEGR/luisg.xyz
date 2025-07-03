<script lang="ts">
  export let currentSection: string;
  
  let mobileMenuOpen = false;

  function scrollToSection(sectionId: string) {
    const element = document.getElementById(sectionId);
    if (element) {
      element.scrollIntoView({ behavior: 'smooth' });
    }
    mobileMenuOpen = false;
  }

  function toggleMobileMenu() {
    mobileMenuOpen = !mobileMenuOpen;
  }
</script>

<header class="header">
  <div class="container">
    <div class="logo">
      <h2>Luis G</h2>
    </div>
    
    <nav class="nav" class:nav-open={mobileMenuOpen}>
      <a 
        href="#home" 
        class:active={currentSection === 'home'}
        on:click={() => scrollToSection('home')}
      >
        Home
      </a>
      <a 
        href="#about" 
        class:active={currentSection === 'about'}
        on:click={() => scrollToSection('about')}
      >
        About
      </a>
      <a 
        href="#projects" 
        class:active={currentSection === 'projects'}
        on:click={() => scrollToSection('projects')}
      >
        Projects
      </a>
      <a 
        href="#gallery" 
        class:active={currentSection === 'gallery'}
        on:click={() => scrollToSection('gallery')}
      >
        Gallery
      </a>
      <a 
        href="#contact" 
        class:active={currentSection === 'contact'}
        on:click={() => scrollToSection('contact')}
      >
        Contact
      </a>
    </nav>

    <button class="mobile-menu-btn" on:click={toggleMobileMenu}>
      <span></span>
      <span></span>
      <span></span>
    </button>
  </div>
</header>

<style>
  .header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background: rgba(255, 255, 255, 0.95);
    backdrop-filter: blur(10px);
    z-index: 1000;
    border-bottom: 1px solid rgba(0, 0, 0, 0.1);
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 70px;
  }

  .logo h2 {
    margin: 0;
    font-size: 1.5rem;
    font-weight: 700;
    color: #2563eb;
  }

  .nav {
    display: flex;
    gap: 2rem;
  }

  .nav a {
    text-decoration: none;
    color: #374151;
    font-weight: 500;
    transition: color 0.3s ease;
    position: relative;
  }

  .nav a:hover,
  .nav a.active {
    color: #2563eb;
  }

  .nav a.active::after {
    content: '';
    position: absolute;
    bottom: -5px;
    left: 0;
    right: 0;
    height: 2px;
    background: #2563eb;
  }

  .mobile-menu-btn {
    display: none;
    flex-direction: column;
    background: none;
    border: none;
    cursor: pointer;
    padding: 0.5rem;
  }

  .mobile-menu-btn span {
    width: 25px;
    height: 3px;
    background: #374151;
    margin: 3px 0;
    transition: 0.3s;
  }

  @media (max-width: 768px) {
    .nav {
      position: fixed;
      top: 70px;
      left: 0;
      right: 0;
      background: white;
      flex-direction: column;
      padding: 2rem;
      transform: translateY(-100%);
      opacity: 0;
      visibility: hidden;
      transition: all 0.3s ease;
      border-bottom: 1px solid rgba(0, 0, 0, 0.1);
    }

    .nav.nav-open {
      transform: translateY(0);
      opacity: 1;
      visibility: visible;
    }

    .mobile-menu-btn {
      display: flex;
    }
  }
</style> 