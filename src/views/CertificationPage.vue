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
        logoUrl: require(''),
        name: 'Certificate 1',
        issuer: 'Coursera',
        date: 'March 2023',
        description:
          'Completed a comprehensive course on Data Analysis with Python, covering various libraries and techniques for effective data handling.',
      },
      {
        id: 2,
        logoUrl: require(''),
        name: 'Certificate 2',
        issuer: 'Udacity',
        date: 'January 2023',
        description:
          'Completed the Nanodegree program in Data Analysis, learning advanced techniques and tools such as SQL, Excel, and Power BI.',
      },
      {
        id: 3,
        logoUrl: require(''),
        name: 'Certificate 3',
        issuer: 'DataCamp',
        date: 'November 2022',
        description:
          'Earned certification in Data Science, focusing on Python, R, and various machine learning techniques.',
      },
      {
        id: 4,
        logoUrl: require(''),
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
  display: grid;
  justify-items: center;
  justify-content: center;
  padding-bottom: 9.6rem;
  position: relative;
  color: #dee2e6;
}
.certificate-title-container {
  margin-top: 2.4rem;
  position: relative;
}
h2 {
  font-size: 3.2rem;
  letter-spacing: 0.1rem;
  text-shadow: 2px 2px #52b788;
}
.rectangle {
  background: #333533;
  position: absolute;
  left: -1%;
  width: 100%;
  top: 10%;
  height: 2rem;
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
  display: flex;
  flex-wrap: wrap;
  gap: 3.2rem;
}
.certification-logo {
  width: 8rem;
  height: 8rem;
  border-radius: 50%;
  border: 5px solid #40916c;
}
.certification-details {
  display: flex;
  flex-direction: column;
}
.certification-name {
  font-size: 2.4rem;
  color: #52b788;
}
.certification-issuer {
  font-size: 1.8rem;
}
.certification-date {
  font-size: 1.8rem;
  color: #a9a9a9;
}
.certification-description {
  font-size: 1.6rem;
  margin-top: 1rem;
}
@media (max-width: 768px) {
  h2 {
    font-size: 2.4rem;
  }
  .rectangle {
    height: 1.6rem;
  }
}
</style>