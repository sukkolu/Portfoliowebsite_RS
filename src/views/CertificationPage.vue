<template>
  <section class="certificate-section">
    <base-background></base-background>
    <div class="certificate-title-container">
      <div class="rectangle" v-if="show"></div>
      <h2>Certifications</h2>
    </div>
    <div class="certification-container" v-if="show">
      <base-card v-for="certificate in certificates" :key="certificate.id">
        <template #image>
          <img
            :src="certificate.imageUrl"
            :alt="`Image of ${certificate.name}`"
            class="certification-image"
          />
        </template>
        <template #content>
          <div class="certification-details">
            <div class="certification-name">{{ certificate.name }}</div>
            <div class="certification-issuer">
              Issuer: {{ certificate.issuer }}
            </div>
            <div class="certification-date">Date: {{ certificate.date }}</div>
            <div class="certification-description">
              <p>{{ certificate.description }}</p>
            </div>
          </div>
        </template>
        <template #button-1>
          <button class="view-button">View Certificate</button>
        </template>
      </base-card>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';
import useAnimation from '../mixins/animation';
import BaseBackground from '../components/UI/BaseBackground.vue';
import BaseCard from '../components/UI/BaseCard.vue';

// Ensure to register components
// Use import for assets
const certificates = ref([
  {
    id: 1,
    imageUrl: new URL('@/assets/certificate1.png', import.meta.url).href,
    name: 'Certificate 1',
    issuer: 'iNeuron.ai',
    date: '7th May 2024',
    description:
      'Completed a comprehensive course on Data Analysis with Python, covering various libraries and techniques for effective data handling.',
  },
  {
    id: 2,
    imageUrl: new URL('@/assets/certificate2.png', import.meta.url).href,
    name: 'Certificate 2',
    issuer: 'HackerRank',
    date: '30th September 2023',
    description:
      'Completed the Nanodegree program in Data Analysis, learning advanced techniques and tools such as SQL, Excel, and Power BI.',
  },
]);

// Initialize animation and set `show` accordingly
const { show } = useAnimation();
</script>

<style scoped>
.certificate-section {
  width: 100%;
  background: #333533;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2rem 1rem;
  color: #dee2e6;
}

.certificate-title-container {
  margin-top: 2.4rem;
  position: relative;
  text-align: center;
}

h2 {
  font-size: 12.6rem;
  letter-spacing: 3px;
  text-shadow: 5px 5px #52b788;
  padding-right: 1.2rem;
}

.rectangle {
  background: #333533;
  position: absolute;
  left: -1%;
  width: 100%;
  top: 10%;
  height: 16rem;
  border-left: 10px solid #40916c;
  animation: moveRect 1s 1 cubic-bezier(0.175, 0.885, 0.32, 1) forwards;
}

@keyframes moveRect {
  0% {
    left: 0;
  }
  100% {
    left: 100%;
    width: 1%;
  }
}

.certification-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  width: 100%;
  margin-top: 2rem;
}

.certification-image {
  width: 100%;
  height: auto;
  border-radius: 10px;
  border: 3px solid #40916c;
}

.certification-details {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.certification-name {
  font-size: 1.8rem;
  color: #52b788;
}

.certification-issuer,
.certification-date {
  font-size: 1.4rem;
}

.certification-description {
  font-size: 1.2rem;
  margin-top: 0.5rem;
}

.view-button {
  background-color: #40916c;
  color: #fff;
  padding: 0.8rem 1.6rem;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1.4rem;
}

.view-button:hover {
  background-color: #52b788;
}

@media (max-width: 768px) {
  h2 {
    font-size: 9.6rem;
  }

  .rectangle {
    height: 12rem;
  }

  .certification-image {
    width: 100%;
  }

  .certification-name {
    font-size: 1.6rem;
  }

  .certification-issuer,
  .certification-date {
    font-size: 1.2rem;
  }

  .certification-description {
    font-size: 1rem;
  }
}

@media (max-width: 480px) {
  h2 {
    font-size: 8rem;
  }

  .rectangle {
    height: 10rem;
  }

  .certification-image {
    width: 100%;
  }

  .certification-name {
    font-size: 1.4rem;
  }

  .certification-issuer,
  .certification-date {
    font-size: 1rem;
  }

  .certification-description {
    font-size: 0.9rem;
  }
}

@media (max-width: 350px) {
  h2 {
    font-size: 6.4rem;
  }

  .rectangle {
    height: 8rem;
  }

  .certification-image {
    width: 100%;
  }

  .certification-name {
    font-size: 1.2rem;
  }

  .certification-issuer,
  .certification-date {
    font-size: 0.8rem;
  }

  .certification-description {
    font-size: 0.8rem;
  }
}
</style>