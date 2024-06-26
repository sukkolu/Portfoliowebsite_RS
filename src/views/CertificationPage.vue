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
            <div class="certification-issuer">Issuer: {{ certificate.issuer }}</div>
            <div class="certification-date">Date: {{ certificate.date }}</div>
            <div class="certification-description">
              <p>{{ certificate.description }}</p>
            </div>
            <button class="view-button" @click="viewCertificate(certificate.url)">View Certificate</button>
          </div>
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

const certificates = ref([
  {
    id: 1,
    imageUrl: new URL('@/assets/Ineroun.svg', import.meta.url).href,
    name: 'Certificate 1',
    issuer: 'iNeuron.ai',
    date: '7th May 2024',
    description:
      'Completed a comprehensive course on Data Analysis with Python, covering various libraries and techniques for effective data handling.',
    url: 'https://drive.google.com/file/d/1k6__S8e0InhA-7g_nhSBroFvr08X0Iy4/view?usp=drive_link', // Replace with actual URL
  },
  {
    id: 2,
    imageUrl: new URL('@/assets/sql_certificate.svg', import.meta.url).href,
    name: 'Certificate 2',
    issuer: 'HackerRank',
    date: '30th September 2023',
    description:
      'Completed the Nanodegree program in Data Analysis, learning advanced techniques and tools such as SQL, Excel, and Power BI.',
    url: 'https://drive.google.com/file/d/13IckWcIjudGr-QNyfCXO_JU44QLwAhZ5/view?usp=drive_link', // Replace with actual URL
  },
]);

const { show } = useAnimation();

const viewCertificate = (url) => {
  window.open(url, '_blank');
};
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
  font-size: 3rem;
  letter-spacing: 1px;
  text-shadow: 2px 2px #52b788;
  padding-right: 1.2rem;
  margin: 0;
}

.rectangle {
  background: #333533;
  position: absolute;
  left: -1%;
  width: 100%;
  top: 10%;
  height: 3.5rem;
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
  padding: 0 1rem;
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
  margin-top: 1rem;
}

.view-button:hover {
  background-color: #52b788;
}

@media (max-width: 768px) {
  h2 {
    font-size: 2.4rem;
  }

  .rectangle {
    height: 2.4rem;
  }

  .certification-container {
    padding: 0 2rem;
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
    font-size: 2rem;
  }

  .rectangle {
    height: 2rem;
  }

  .certification-container {
    padding: 0 1.5rem;
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

  .view-button {
    font-size: 1.2rem;
    padding: 0.6rem 1.2rem;
  }
}

@media (max-width: 350px) {
  h2 {
    font-size: 1.6rem;
  }

  .rectangle {
    height: 1.6rem;
  }

  .certification-container {
    padding: 0 1rem;
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

  .view-button {
    font-size: 1rem;
    padding: 0.5rem 1rem;
  }
}
</style>
