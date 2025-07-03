<script lang="ts">
  import { onMount } from 'svelte';
  import Header from './components/Header.svelte';
  import Hero from './components/Hero.svelte';
  import About from './components/About.svelte';
  import Projects from './components/Projects.svelte';
  import Gallery from './components/Gallery.svelte';
  import Contact from './components/Contact.svelte';
  import Footer from './components/Footer.svelte';

  let currentSection = 'home';

  function handleScroll() {
    const sections = ['home', 'about', 'projects', 'gallery', 'contact'];
    const scrollPosition = window.scrollY + 100;

    for (const section of sections) {
      const element = document.getElementById(section);
      if (element) {
        const offsetTop = element.offsetTop;
        const offsetHeight = element.offsetHeight;
        
        if (scrollPosition >= offsetTop && scrollPosition < offsetTop + offsetHeight) {
          currentSection = section;
          break;
        }
      }
    }
  }

  onMount(() => {
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });
</script>

<main>
  <Header {currentSection} />
  <Hero />
  <About />
  <Projects />
  <Gallery />
  <Contact />
  <Footer />
</main>

<style>
  main {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    line-height: 1.6;
    color: #333;
  }

  :global(body) {
    margin: 0;
    padding: 0;
    background-color: #fafafa;
  }

  :global(*) {
    box-sizing: border-box;
  }
</style> 