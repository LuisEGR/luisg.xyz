<script lang="ts">
  function scrollToSection(sectionId: string) {
    const element = document.getElementById(sectionId);
    if (element) {
      element.scrollIntoView({ behavior: 'smooth' });
    }
  }
</script>

<section id="home" class="hero">
  <div class="container">
    <div class="hero-content">
      <h1 class="hero-title">
        Hi, I'm <span class="highlight">Luis G</span>
      </h1>
      <p class="hero-subtitle">
        Developer, Drone Enthusiast, and Creator
      </p>
      <p class="hero-description">
        I build amazing digital experiences and capture stunning aerial perspectives. 
        Welcome to my corner of the internet where code meets creativity.
      </p>
      <div class="hero-buttons">
        <button class="btn btn-primary" on:click={() => scrollToSection('projects')}>
          View My Work
        </button>
        <button class="btn btn-secondary" on:click={() => scrollToSection('about')}>
          Learn More
        </button>
      </div>
    </div>
    <div class="hero-visual">
      <div class="floating-card">
        <div class="code-snippet">
          <div class="code-line">
            <span class="keyword">const</span> <span class="variable">luis</span> = &#123;
          </div>
          <div class="code-line indent">
            <span class="property">passion</span>: <span class="string">'coding'</span>,
          </div>
          <div class="code-line indent">
            <span class="property">hobby</span>: <span class="string">'drones'</span>,
          </div>
          <div class="code-line indent">
            <span class="property">goal</span>: <span class="string">'create amazing things'</span>
          </div>
          <div class="code-line">
            &#125;;
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    padding: 2rem 0;
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 2rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
  }

  .hero-title {
    font-size: 3.5rem;
    font-weight: 700;
    margin: 0 0 1rem 0;
    line-height: 1.2;
  }

  .highlight {
    color: #fbbf24;
  }

  .hero-subtitle {
    font-size: 1.5rem;
    margin: 0 0 1.5rem 0;
    opacity: 0.9;
  }

  .hero-description {
    font-size: 1.1rem;
    margin: 0 0 2rem 0;
    opacity: 0.8;
    line-height: 1.6;
  }

  .hero-buttons {
    display: flex;
    gap: 1rem;
  }

  .btn {
    padding: 0.75rem 2rem;
    border: none;
    border-radius: 0.5rem;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
    text-decoration: none;
    display: inline-block;
  }

  .btn-primary {
    background: #fbbf24;
    color: #1f2937;
  }

  .btn-primary:hover {
    background: #f59e0b;
    transform: translateY(-2px);
  }

  .btn-secondary {
    background: transparent;
    color: white;
    border: 2px solid white;
  }

  .btn-secondary:hover {
    background: white;
    color: #1f2937;
    transform: translateY(-2px);
  }

  .hero-visual {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .floating-card {
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(10px);
    border-radius: 1rem;
    padding: 2rem;
    border: 1px solid rgba(255, 255, 255, 0.2);
    animation: float 6s ease-in-out infinite;
  }

  .code-snippet {
    font-family: 'Fira Code', 'Monaco', 'Consolas', monospace;
    font-size: 0.9rem;
    line-height: 1.5;
  }

  .code-line {
    margin: 0;
  }

  .code-line.indent {
    padding-left: 2rem;
  }

  .keyword {
    color: #fbbf24;
  }

  .variable {
    color: #60a5fa;
  }

  .property {
    color: #34d399;
  }

  .string {
    color: #f87171;
  }

  @keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-20px); }
  }

  @media (max-width: 768px) {
    .container {
      grid-template-columns: 1fr;
      text-align: center;
      gap: 2rem;
    }

    .hero-title {
      font-size: 2.5rem;
    }

    .hero-buttons {
      justify-content: center;
      flex-wrap: wrap;
    }

    .floating-card {
      padding: 1.5rem;
    }

    .code-snippet {
      font-size: 0.8rem;
    }
  }
</style> 