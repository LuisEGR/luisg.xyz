<script lang="ts">
  const photos = [
    {
      id: 1,
      title: 'Sunset Over Mountains',
      description: 'Captured during golden hour in the Rocky Mountains',
      image: 'https://placehold.co/400x300/ff6b6b/ffffff?text=Sunset+Mountains',
      driveLink: 'https://drive.google.com/file/d/your-file-id-1/view',
      category: 'landscape'
    },
    {
      id: 2,
      title: 'City Skyline',
      description: 'Aerial view of downtown during blue hour',
      image: 'https://placehold.co/400x300/4ecdc4/ffffff?text=City+Skyline',
      driveLink: 'https://drive.google.com/file/d/your-file-id-2/view',
      category: 'urban'
    },
    {
      id: 3,
      title: 'Coastal Cliffs',
      description: 'Dramatic cliffs meeting the ocean waves',
      image: 'https://placehold.co/400x300/45b7d1/ffffff?text=Coastal+Cliffs',
      driveLink: 'https://drive.google.com/file/d/your-file-id-3/view',
      category: 'nature'
    },
    {
      id: 4,
      title: 'Forest Canopy',
      description: 'Looking down through the dense forest canopy',
      image: 'https://placehold.co/400x300/96ceb4/ffffff?text=Forest+Canopy',
      driveLink: 'https://drive.google.com/file/d/your-file-id-4/view',
      category: 'nature'
    },
    {
      id: 5,
      title: 'Desert Dunes',
      description: 'Rolling sand dunes in the golden desert',
      image: 'https://placehold.co/400x300/ffeaa7/ffffff?text=Desert+Dunes',
      driveLink: 'https://drive.google.com/file/d/your-file-id-5/view',
      category: 'landscape'
    },
    {
      id: 6,
      title: 'Industrial Complex',
      description: 'Geometric patterns of modern architecture',
      image: 'https://placehold.co/400x300/dda0dd/ffffff?text=Industrial+Complex',
      driveLink: 'https://drive.google.com/file/d/your-file-id-6/view',
      category: 'urban'
    }
  ];

  let selectedCategory = 'all';
  let selectedPhoto: typeof photos[0] | null = null;

  $: filteredPhotos = selectedCategory === 'all' 
    ? photos 
    : photos.filter(photo => photo.category === selectedCategory);

  function openPhotoModal(photo: typeof photos[0]) {
    selectedPhoto = photo;
  }

  function closePhotoModal() {
    selectedPhoto = null;
  }
</script>

<section id="gallery" class="gallery">
  <div class="container">
    <div class="section-header">
      <h2>Drone Photography</h2>
      <p>Aerial perspectives from around the world</p>
    </div>

    <div class="filter-buttons">
      <button 
        class="filter-btn" 
        class:active={selectedCategory === 'all'}
        on:click={() => selectedCategory = 'all'}
      >
        All
      </button>
      <button 
        class="filter-btn" 
        class:active={selectedCategory === 'landscape'}
        on:click={() => selectedCategory = 'landscape'}
      >
        Landscapes
      </button>
      <button 
        class="filter-btn" 
        class:active={selectedCategory === 'urban'}
        on:click={() => selectedCategory = 'urban'}
      >
        Urban
      </button>
      <button 
        class="filter-btn" 
        class:active={selectedCategory === 'nature'}
        on:click={() => selectedCategory = 'nature'}
      >
        Nature
      </button>
    </div>

    <div class="gallery-grid">
      {#each filteredPhotos as photo}
        <div class="photo-card" on:click={() => openPhotoModal(photo)}>
          <div class="photo-image">
            <img src={photo.image} alt={photo.title} />
            <div class="photo-overlay">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9zM5 18v2h14v-2H5z"/>
              </svg>
            </div>
          </div>
          <div class="photo-info">
            <h3>{photo.title}</h3>
            <p>{photo.description}</p>
          </div>
        </div>
      {/each}
    </div>
  </div>

  {#if selectedPhoto}
    <div class="modal-overlay" on:click={closePhotoModal}>
      <div class="modal-content" on:click|stopPropagation>
        <button class="modal-close" on:click={closePhotoModal}>
          <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
            <path d="M19 6.41L17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12z"/>
          </svg>
        </button>
        <div class="modal-image">
          <img src={selectedPhoto.image} alt={selectedPhoto.title} />
        </div>
        <div class="modal-info">
          <h3>{selectedPhoto.title}</h3>
          <p>{selectedPhoto.description}</p>
          <a 
            href={selectedPhoto.driveLink} 
            target="_blank" 
            rel="noopener noreferrer" 
            class="download-btn"
          >
            <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
              <path d="M19 9h-4V3H9v6H5l7 7 7-7zM5 18v2h14v-2H5z"/>
            </svg>
            View Full Resolution
          </a>
        </div>
      </div>
    </div>
  {/if}
</section>

<style>
  .gallery {
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

  .gallery-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
  }

  .photo-card {
    background: white;
    border-radius: 1rem;
    overflow: hidden;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
    cursor: pointer;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .photo-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
  }

  .photo-image {
    position: relative;
    height: 250px;
    overflow: hidden;
  }

  .photo-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s ease;
  }

  .photo-card:hover .photo-image img {
    transform: scale(1.05);
  }

  .photo-overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0;
    transition: opacity 0.3s ease;
    color: white;
  }

  .photo-card:hover .photo-overlay {
    opacity: 1;
  }

  .photo-info {
    padding: 1.5rem;
  }

  .photo-info h3 {
    font-size: 1.25rem;
    font-weight: 600;
    color: #1f2937;
    margin: 0 0 0.5rem 0;
  }

  .photo-info p {
    color: #6b7280;
    line-height: 1.6;
    margin: 0;
  }

  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.9);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 2000;
    padding: 2rem;
  }

  .modal-content {
    background: white;
    border-radius: 1rem;
    max-width: 90vw;
    max-height: 90vh;
    overflow: hidden;
    position: relative;
  }

  .modal-close {
    position: absolute;
    top: 1rem;
    right: 1rem;
    background: rgba(0, 0, 0, 0.5);
    border: none;
    color: white;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 10;
  }

  .modal-image {
    width: 100%;
    max-height: 60vh;
    overflow: hidden;
  }

  .modal-image img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }

  .modal-info {
    padding: 2rem;
  }

  .modal-info h3 {
    font-size: 1.5rem;
    font-weight: 600;
    color: #1f2937;
    margin: 0 0 1rem 0;
  }

  .modal-info p {
    color: #6b7280;
    line-height: 1.6;
    margin: 0 0 1.5rem 0;
  }

  .download-btn {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    padding: 0.75rem 1.5rem;
    background: #2563eb;
    color: white;
    text-decoration: none;
    border-radius: 0.5rem;
    font-weight: 500;
    transition: background 0.3s ease;
  }

  .download-btn:hover {
    background: #1d4ed8;
  }

  @media (max-width: 768px) {
    .gallery-grid {
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

    .modal-content {
      max-width: 95vw;
      max-height: 95vh;
    }

    .modal-info {
      padding: 1.5rem;
    }
  }
</style> 