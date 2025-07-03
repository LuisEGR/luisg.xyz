<script lang="ts">
  const socialLinks = [
    {
      name: 'GitHub',
      url: 'https://github.com/yourusername',
      icon: `<svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
        <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
      </svg>`
    },
    {
      name: 'LinkedIn',
      url: 'https://linkedin.com/in/yourusername',
      icon: `<svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
        <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
      </svg>`
    },
    {
      name: 'Twitter',
      url: 'https://twitter.com/yourusername',
      icon: `<svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
        <path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/>
      </svg>`
    },
    {
      name: 'Instagram',
      url: 'https://instagram.com/yourusername',
      icon: `<svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
        <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
      </svg>`
    }
  ];

  const contactInfo = [
    {
      type: 'email',
      label: 'Email',
      value: 'luis@example.com',
      icon: `<svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
        <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
      </svg>`
    },
    {
      type: 'location',
      label: 'Location',
      value: 'Your City, Country',
      icon: `<svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
        <path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/>
      </svg>`
    }
  ];

  function copyToClipboard(text: string) {
    navigator.clipboard.writeText(text).then(() => {
      // You could add a toast notification here
      console.log('Copied to clipboard:', text);
    });
  }
</script>

<section id="contact" class="contact">
  <div class="container">
    <div class="section-header">
      <h2>Get In Touch</h2>
      <p>Let's connect and create something amazing together</p>
    </div>

    <div class="contact-content">
      <div class="contact-info">
        <h3>Contact Information</h3>
        <p>
          I'm always open to discussing new opportunities, interesting projects, 
          or just having a chat about technology and drones. Feel free to reach out!
        </p>

        <div class="contact-details">
          {#each contactInfo as contact}
            <div class="contact-item" on:click={() => copyToClipboard(contact.value)}>
              <div class="contact-icon" innerHTML={contact.icon}></div>
              <div class="contact-text">
                <span class="contact-label">{contact.label}</span>
                <span class="contact-value">{contact.value}</span>
              </div>
            </div>
          {/each}
        </div>

        <div class="social-links">
          <h4>Follow Me</h4>
          <div class="social-grid">
            {#each socialLinks as social}
              <a 
                href={social.url} 
                target="_blank" 
                rel="noopener noreferrer" 
                class="social-link"
                title={social.name}
              >
                <div innerHTML={social.icon}></div>
                <span>{social.name}</span>
              </a>
            {/each}
          </div>
        </div>
      </div>

      <div class="contact-form">
        <h3>Send Me a Message</h3>
        <form class="form">
          <div class="form-group">
            <label for="name">Name</label>
            <input type="text" id="name" name="name" required />
          </div>
          
          <div class="form-group">
            <label for="email">Email</label>
            <input type="email" id="email" name="email" required />
          </div>
          
          <div class="form-group">
            <label for="subject">Subject</label>
            <input type="text" id="subject" name="subject" required />
          </div>
          
          <div class="form-group">
            <label for="message">Message</label>
            <textarea id="message" name="message" rows="5" required></textarea>
          </div>
          
          <button type="submit" class="submit-btn">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
              <path d="M2.01 21L23 12 2.01 3 2 10l15 2-15 2z"/>
            </svg>
            Send Message
          </button>
        </form>
      </div>
    </div>
  </div>
</section>

<style>
  .contact {
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

  .contact-content {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
  }

  .contact-info h3,
  .contact-form h3 {
    font-size: 1.5rem;
    font-weight: 600;
    color: #1f2937;
    margin: 0 0 1rem 0;
  }

  .contact-info p {
    color: #6b7280;
    line-height: 1.7;
    margin: 0 0 2rem 0;
  }

  .contact-details {
    margin-bottom: 2rem;
  }

  .contact-item {
    display: flex;
    align-items: center;
    gap: 1rem;
    padding: 1rem;
    background: white;
    border-radius: 0.5rem;
    margin-bottom: 1rem;
    cursor: pointer;
    transition: all 0.3s ease;
    border: 1px solid #e5e7eb;
  }

  .contact-item:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
    border-color: #2563eb;
  }

  .contact-icon {
    color: #2563eb;
    flex-shrink: 0;
  }

  .contact-text {
    display: flex;
    flex-direction: column;
  }

  .contact-label {
    font-size: 0.875rem;
    color: #6b7280;
    font-weight: 500;
  }

  .contact-value {
    color: #1f2937;
    font-weight: 500;
  }

  .social-links h4 {
    font-size: 1.25rem;
    font-weight: 600;
    color: #1f2937;
    margin: 0 0 1rem 0;
  }

  .social-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }

  .social-link {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    padding: 1rem;
    background: white;
    color: #374151;
    text-decoration: none;
    border-radius: 0.5rem;
    border: 1px solid #e5e7eb;
    transition: all 0.3s ease;
  }

  .social-link:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
    border-color: #2563eb;
    color: #2563eb;
  }

  .form {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }

  .form-group {
    display: flex;
    flex-direction: column;
  }

  .form-group label {
    font-weight: 500;
    color: #374151;
    margin-bottom: 0.5rem;
  }

  .form-group input,
  .form-group textarea {
    padding: 0.75rem;
    border: 2px solid #e5e7eb;
    border-radius: 0.5rem;
    font-size: 1rem;
    transition: border-color 0.3s ease;
    background: white;
  }

  .form-group input:focus,
  .form-group textarea:focus {
    outline: none;
    border-color: #2563eb;
  }

  .form-group textarea {
    resize: vertical;
    min-height: 120px;
  }

  .submit-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    padding: 1rem 2rem;
    background: #2563eb;
    color: white;
    border: none;
    border-radius: 0.5rem;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
  }

  .submit-btn:hover {
    background: #1d4ed8;
    transform: translateY(-2px);
  }

  @media (max-width: 768px) {
    .contact-content {
      grid-template-columns: 1fr;
      gap: 2rem;
    }

    .section-header h2 {
      font-size: 2rem;
    }

    .social-grid {
      grid-template-columns: 1fr;
    }

    .contact-info h3,
    .contact-form h3 {
      font-size: 1.25rem;
    }
  }
</style> 