<script lang="ts">
  const skills = [
    { name: 'Angular', level: 90, color: '#dd0031' },
    { name: 'Svelte', level: 85, color: '#ff3e00' },
    { name: 'React', level: 75, color: '#61dafb' },
    { name: 'TypeScript', level: 85, color: '#3178c6' },
    { name: 'JavaScript', level: 90, color: '#f7df1e' },
    { name: 'Node.js', level: 80, color: '#339933' },
    { name: 'Python', level: 70, color: '#3776ab' },
    { name: 'Git', level: 85, color: '#f05032' }
  ];

  const interests = [
    'Web Development',
    'Drone Photography',
    'Open Source',
    'UI/UX Design',
    'Cloud Computing',
    'Mobile Development'
  ];
</script>

<section id="about" class="about">
  <div class="container">
    <div class="section-header">
      <h2>About Me</h2>
      <p>Get to know me better</p>
    </div>

    <div class="about-content">
      <div class="about-text">
        <h3>Who I Am</h3>
        <p>
          I'm a passionate developer with a love for creating beautiful, functional, and user-friendly applications. 
          When I'm not coding, you'll find me flying my drone, capturing stunning aerial shots of landscapes and cityscapes.
        </p>
        
        <p>
          With expertise in modern web technologies like Angular, Svelte, and React, I enjoy building 
          applications that not only work flawlessly but also provide an exceptional user experience. 
          I believe in clean code, continuous learning, and pushing the boundaries of what's possible.
        </p>

        <h3>What I Do</h3>
        <p>
          I specialize in frontend development with a focus on creating responsive, accessible, and 
          performant web applications. My experience spans from small business websites to complex 
          enterprise applications.
        </p>

        <div class="interests">
          <h3>Interests & Hobbies</h3>
          <div class="interest-tags">
            {#each interests as interest}
              <span class="interest-tag">{interest}</span>
            {/each}
          </div>
        </div>
      </div>

      <div class="skills-section">
        <h3>Technical Skills</h3>
        <div class="skills">
          {#each skills as skill}
            <div class="skill-item">
              <div class="skill-header">
                <span class="skill-name">{skill.name}</span>
                <span class="skill-level">{skill.level}%</span>
              </div>
              <div class="skill-bar">
                <div 
                  class="skill-progress" 
                  style="width: {skill.level}%; background-color: {skill.color}"
                ></div>
              </div>
            </div>
          {/each}
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .about {
    padding: 5rem 0;
    background: white;
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 2rem;
  }

  .section-header {
    text-align: center;
    margin-bottom: 4rem;
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

  .about-content {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: start;
  }

  .about-text h3 {
    font-size: 1.5rem;
    font-weight: 600;
    color: #1f2937;
    margin: 0 0 1rem 0;
  }

  .about-text p {
    font-size: 1rem;
    line-height: 1.7;
    color: #4b5563;
    margin: 0 0 1.5rem 0;
  }

  .interests {
    margin-top: 2rem;
  }

  .interest-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-top: 1rem;
  }

  .interest-tag {
    background: #f3f4f6;
    color: #374151;
    padding: 0.5rem 1rem;
    border-radius: 2rem;
    font-size: 0.875rem;
    font-weight: 500;
  }

  .skills-section h3 {
    font-size: 1.5rem;
    font-weight: 600;
    color: #1f2937;
    margin: 0 0 2rem 0;
  }

  .skills {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }

  .skill-item {
    width: 100%;
  }

  .skill-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 0.5rem;
  }

  .skill-name {
    font-weight: 500;
    color: #374151;
  }

  .skill-level {
    font-size: 0.875rem;
    color: #6b7280;
  }

  .skill-bar {
    width: 100%;
    height: 8px;
    background: #e5e7eb;
    border-radius: 4px;
    overflow: hidden;
  }

  .skill-progress {
    height: 100%;
    border-radius: 4px;
    transition: width 1s ease-in-out;
  }

  @media (max-width: 768px) {
    .about-content {
      grid-template-columns: 1fr;
      gap: 2rem;
    }

    .section-header h2 {
      font-size: 2rem;
    }

    .about-text h3,
    .skills-section h3 {
      font-size: 1.25rem;
    }
  }
</style> 