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
            :src="certificate.logoUrl"
            :alt="`Image of ${certificate.name}`"
            class="certification-logo"
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
      </base-card>
    </div>
  </section>
</template>

<script>
import { ref } from 'vue';
import useAnimation from '../mixins/animation';
import BaseBackground from '../components/UI/BaseBackground.vue';
import BaseCard from '../components/UI/BaseCard.vue';

export default {
  name: 'CertificationSection',
  components: {
    'base-background': BaseBackground,
    'base-card': BaseCard
  },
  setup() {
    const { show } = useAnimation();
    const certificates = ref([
      {
        id: 1,
        logoUrl: require('@/assets/certificate1-logo.png'),
        name: 'Certificate 1',
        issuer: 'Coursera',
        date: 'March 2023',
        description:
          'Completed a comprehensive course on Data Analysis with Python, covering various libraries and techniques for effective data handling.',
      },
      {
        id: 2,
        logoUrl: require('@/assets/certificate2-logo.png'),
        name: 'Certificate 2',
        issuer: 'Udacity',
        date: 'January 2023',
        description:
          'Completed the Nanodegree program in Data Analysis, learning advanced techniques and tools such as SQL, Excel, and Power BI.',
      },
      {
        id: 3,
        logoUrl: require('@/assets/certificate3-logo.png'),
        name: 'Certificate 3',
        issuer: 'DataCamp',
        date: 'November 2022',
        description:
          'Earned certification in Data Science, focusing on Python, R, and various machine learning techniques.',
      },
      {
        id: 4,
        logoUrl: require('@/assets/certificate4-logo.png'),
        name: 'Certificate 4',
        issuer: 'LinkedIn Learning',
        date: 'September 2022',
        description:
          'Completed a course on Advanced Excel for Data Analysis, mastering complex formulas, data visualization, and pivot tables.',
      },
    ]);

    return { show, certificates };
  },
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
  font-size: 2.4rem;
  letter-spacing: 0.1rem;
  text-shadow: 2px 2px #52b788;
}

.rectangle {
  background: #333533;
  position: absolute;
  left: -1%;
  width: 100%;
  top: 10%;
  height: 1.6rem;
  border-left: 5px solid #40916c;
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

.certification-logo {
  width: 6rem;
  height: 6rem;
  border-radius: 50%;
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

@media (max-width: 768px) {
  h2 {
    font-size: 2rem;
  }

  .rectangle {
    height: 1.2rem;
  }

  .certification-logo {
    width: 5rem;
    height: 5rem;
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
    font-size: 1.6rem;
  }

  .rectangle {
    height: 1rem;
  }

  .certification-logo {
    width: 4rem;
    height: 4rem;
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
</style>