<script lang="ts">
  const projects = [
    {
      id: 1,
      title: 'E-Commerce Platform',
      description: 'A full-stack e-commerce solution built with Angular and Node.js. Features include user authentication, product management, shopping cart, and payment integration.',
      technologies: ['Angular', 'Node.js', 'MongoDB', 'Stripe'],
      image: 'https://placehold.co/400x250/667eea/ffffff?text=E-Commerce',
      github: 'https://github.com/yourusername/ecommerce-platform',
      live: 'https://ecommerce-demo.com',
      featured: true
    },
    {
      id: 2,
      title: 'Task Management App',
      description: 'A collaborative task management application with real-time updates, drag-and-drop functionality, and team collaboration features.',
      technologies: ['Svelte', 'Firebase', 'Tailwind CSS'],
      image: 'https://placehold.co/400x250/764ba2/ffffff?text=Task+App',
      github: 'https://github.com/yourusername/task-manager',
      live: 'https://task-manager-demo.com',
      featured: true
    },
    {
      id: 3,
      title: 'Weather Dashboard',
      description: 'A beautiful weather application that displays current weather and forecasts with interactive maps and location-based services.',
      technologies: ['React', 'TypeScript', 'OpenWeather API'],
      image: 'https://placehold.co/400x250/f093fb/ffffff?text=Weather+App',
      github: 'https://github.com/yourusername/weather-dashboard',
      live: 'https://weather-demo.com',
      featured: false
    },
    {
      id: 4,
      title: 'Portfolio Website',
      description: 'A responsive portfolio website built with modern web technologies, featuring smooth animations and optimal performance.',
      technologies: ['Svelte', 'Vite', 'CSS3'],
      image: 'https://placehold.co/400x250/4facfe/ffffff?text=Portfolio',
      github: 'https://github.com/yourusername/portfolio',
      live: 'https://portfolio-demo.com',
      featured: false
    },
    {
      id: 5,
      title: 'Chat Application',
      description: 'Real-time chat application with user authentication, message history, and file sharing capabilities.',
      technologies: ['Angular', 'Socket.io', 'Express'],
      image: 'https://placehold.co/400x250/43e97b/ffffff?text=Chat+App',
      github: 'https://github.com/yourusername/chat-app',
      live: 'https://chat-demo.com',
      featured: false
    },
    {
      id: 6,
      title: 'Recipe Finder',
      description: 'A recipe discovery app that helps users find recipes based on available ingredients and dietary preferences.',
      technologies: ['React', 'Node.js', 'PostgreSQL'],
      image: 'https://placehold.co/400x250/fa709a/ffffff?text=Recipe+App',
      github: 'https://github.com/yourusername/recipe-finder',
      live: 'https://recipe-demo.com',
      featured: false
    }
  ];

  let selectedFilter = 'all';

  $: filteredProjects = selectedFilter === 'all' 
    ? projects 
    : projects.filter(project => 
        selectedFilter === 'featured' ? project.featured : 
        project.technologies.some(tech => tech.toLowerCase().includes(selectedFilter.toLowerCase()))
      );
</script>

<section id="projects" class="projects">
  <div class="container">
    <div class="section-header">
      <h2>My Projects</h2>
      <p>Some of the things I've built</p>
    </div>

    <div class="filter-buttons">
      <button 
        class="filter-btn" 
        class:active={selectedFilter === 'all'}
        on:click={() => selectedFilter = 'all'}
      >
        All
      </button>
      <button 
        class="filter-btn" 
        class:active={selectedFilter === 'featured'}
        on:click={() => selectedFilter = 'featured'}
      >
        Featured
      </button>
      <button 
        class="filter-btn" 
        class:active={selectedFilter === 'angular'}
        on:click={() => selectedFilter = 'angular'}
      >
        Angular
      </button>
      <button 
        class="filter-btn" 
        class:active={selectedFilter === 'svelte'}
        on:click={() => selectedFilter = 'svelte'}
      >
        Svelte
      </button>
      <button 
        class="filter-btn" 
        class:active={selectedFilter === 'react'}
        on:click={() => selectedFilter = 'react'}
      >
        React
      </button>
    </div>

    <div class="projects-grid">
      {#each filteredProjects as project}
        <div class="project-card" class:featured={project.featured}>
          <div class="project-image">
            <img src={project.image} alt={project.title} />
            {#if project.featured}
              <span class="featured-badge">Featured</span>
            {/if}
          </div>
          <div class="project-content">
            <h3>{project.title}</h3>
            <p>{project.description}</p>
            <div class="project-technologies">
              {#each project.technologies as tech}
                <span class="tech-tag">{tech}</span>
              {/each}
            </div>
            <div class="project-links">
              <a href={project.github} target="_blank" rel="noopener noreferrer" class="project-link">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                </svg>
                Code
              </a>
              <a href={project.live} target="_blank" rel="noopener noreferrer" class="project-link">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                </svg>
                Live Demo
              </a>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .projects {
    padding: 5rem 0;
    background: #f9fafb;
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 2rem;
  }

  .section-header {
    text-align: center;
    margin-bottom: 3rem;
  }

  .section-header h2 {
    font-size: 2.5rem;
    font-weight: 700;
    color: #1f2937;
    margin: 0 0 0.5rem 0;
  }

  .section-header p {
    font-size: 1.1rem;
    color: #6b7280;
    margin: 0;
  }

  .filter-buttons {
    display: flex;
    justify-content: center;
    gap: 1rem;
    margin-bottom: 3rem;
    flex-wrap: wrap;
  }

  .filter-btn {
    padding: 0.5rem 1.5rem;
    border: 2px solid #e5e7eb;
    background: white;
    color: #374151;
    border-radius: 2rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.3s ease;
  }

  .filter-btn:hover,
  .filter-btn.active {
    border-color: #2563eb;
    background: #2563eb;
    color: white;
  }

  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 2rem;
  }

  .project-card {
    background: white;
    border-radius: 1rem;
    overflow: hidden;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .project-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
  }

  .project-card.featured {
    border: 2px solid #fbbf24;
  }

  .project-image {
    position: relative;
    height: 200px;
    overflow: hidden;
  }

  .project-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .featured-badge {
    position: absolute;
    top: 1rem;
    right: 1rem;
    background: #fbbf24;
    color: #1f2937;
    padding: 0.25rem 0.75rem;
    border-radius: 1rem;
    font-size: 0.75rem;
    font-weight: 600;
  }

  .project-content {
    padding: 1.5rem;
  }

  .project-content h3 {
    font-size: 1.25rem;
    font-weight: 600;
    color: #1f2937;
    margin: 0 0 0.75rem 0;
  }

  .project-content p {
    color: #6b7280;
    line-height: 1.6;
    margin: 0 0 1rem 0;
  }

  .project-technologies {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-bottom: 1.5rem;
  }

  .tech-tag {
    background: #f3f4f6;
    color: #374151;
    padding: 0.25rem 0.75rem;
    border-radius: 1rem;
    font-size: 0.75rem;
    font-weight: 500;
  }

  .project-links {
    display: flex;
    gap: 1rem;
  }

  .project-link {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    padding: 0.5rem 1rem;
    background: #f3f4f6;
    color: #374151;
    text-decoration: none;
    border-radius: 0.5rem;
    font-size: 0.875rem;
    font-weight: 500;
    transition: all 0.3s ease;
  }

  .project-link:hover {
    background: #2563eb;
    color: white;
  }

  @media (max-width: 768px) {
    .projects-grid {
      grid-template-columns: 1fr;
    }

    .section-header h2 {
      font-size: 2rem;
    }

    .filter-buttons {
      gap: 0.5rem;
    }

    .filter-btn {
      padding: 0.5rem 1rem;
      font-size: 0.875rem;
    }
  }
</style> 