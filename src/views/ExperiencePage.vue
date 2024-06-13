<template>
  <section class="experience-section">
    <base-background></base-background>
    <div class="experience-title-container">
      <div class="rectangle" v-if="show"></div>
      <h2>Experience</h2>
    </div>
    <div class="experience-container" v-if="show">
      <base-card v-for="experience in experiences" :key="experience.id">
        <template #image>
          <img
            :src="getImageUrl(experience.companyLogoUrl)"
            :alt="`${experience.companyName} Logo`"
            class="company-logo"
          />
        </template>
        <template #content>
          <div class="company-details">
            <div class="company-name">{{ experience.companyName }}</div>
            <div class="company-role">Role: {{ experience.role }}</div>
            <div class="company-duration">
              Duration: {{ experience.startDate }} - {{ experience.endDate }}
            </div>
            <div class="company-description">
              <p>{{ experience.description }}</p>
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
  name: 'ExperienceSection',
  components: {
    'base-background': BaseBackground,
    'base-card': BaseCard
  },
  setup() {
    const show = useAnimation();
    const experiences = ref([
      {
        id: 1,
        companyName: 'Tata Motors Finance',
        companyLogoUrl: 'company1_logo.svg', // Adjust the path as per your project structure
        role: 'Operations Executive',
        startDate: 'Feb 2024',
        endDate: 'Present',
        description:
          "At Tata Motors Finance, I manage vehicle financing, calculate invoices, facilitate loan disbursement, and create SAP contracts. Using Excel's VLOOKUP, data validation, and pivot tables, I analyze customer data for loan eligibility. With Power BI, I create reports for decision-making. I ensure regulatory compliance through documentation management. My expertise includes evaluating loan proposals, assessing risk, and structuring financing.",
      },
      {
        id: 2,
        companyName: 'Accenture',
        companyLogoUrl: 'company2_logo.svg', // Adjust the path as per your project structure
        role: 'Transaction Analyst',
        startDate: 'Aug 2020',
        endDate: 'Sep 2022',
        description:
          'At Accenture, I focused on testing and validating benefit setups for US clients as a PBM Service Provider, ensuring smooth service delivery. As a Client Planner, I efficiently set up plans, clarified requests, and minimized errors. Managing 1,000+ service requests, I showcased adept data management. I led process improvement by developing and executing testing processes. Effective stakeholder communication was ensured through fostering collaboration and meticulous processes.',
      },
    ]);

    const getImageUrl = (imagePath) => {
      return new URL(`../assets/${imagePath}`, import.meta.url).href;
    };

    return { show, experiences, getImageUrl };
  },
};
</script>

<style scoped>
.experience-section {
  height: 100%;
  width: 100%;
  background: #333533;
  display: grid;
  justify-items: center;
  justify-content: center;
  grid-template-rows: auto;
  grid-template-columns: 1fr;
  padding-bottom: 9.6rem;
  row-gap: 4.8rem;
  position: relative;
  color: #dee2e6;
  padding-top: 4.8rem; /* Adjust top padding for better spacing */
}
.experience-title-container {
  margin-top: 2.4rem;
  position: relative;
  grid-column: 1;
  text-align: center; /* Center align the title */
}
h2 {
  font-size: 3.2rem;
  letter-spacing: 0.1rem;
  text-shadow: 2px 2px #52b788;
  padding-right: 1.2rem;
}
.rectangle {
  background: #333533;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  width: 100%;
  top: 10%;
  height: 2rem;
  border-left: 5px solid #40916c;
  animation: moveRect 1s 1 cubic-bezier(0.175, 0.885, 0.32, 1) forwards;
  overflow-x: auto; /* Enable horizontal scrolling */
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
.experience-container {
  grid-column: 1;
  display: flex;
  flex-direction: column; /* Adjust to column layout for mobile */
  align-items: center; /* Center align content */
  gap: 3.2rem;
  overflow-x: hidden; /* Hide horizontal overflow on smaller screens */
}
.company-logo {
  width: 8rem;
  height: 8rem;
  border-radius: 50%;
  border: 5px solid #40916c;
}
.company-details {
  text-align: center; /* Center align company details */
}
.company-name {
  font-size: 2.4rem; /* Reduce font size for better fit */
  color: #52b788;
}
.company-role {
  font-size: 1.8rem; /* Reduce font size for better fit */
}
.company-duration {
  font-size: 1.6rem; /* Reduce font size for better fit */
  color: #a9a9a9;
}
.company-description {
  font-size: 1.4rem; /* Reduce font size for better fit */
  margin-top: 1rem;
  text-align: justify; /* Justify text for better readability */
}
@media (max-width: 992px) {
  h2 {
    font-size: 2.4rem; /* Adjust font size for smaller screens */
  }
  .rectangle {
    height: 1.5rem; /* Adjust height for smaller screens */
  }
  .experience-container {
    padding: 0 1.6rem; /* Add padding for better spacing */
  }
  .company-logo {
    width: 6rem; /* Adjust logo size for smaller screens */
    height: 6rem;
  }
  .company-name {
    font-size: 2rem; /* Further reduce font size for smaller screens */
  }
  .company-role {
    font-size: 1.6rem; /* Further reduce font size for smaller screens */
  }
  .company-duration {
    font-size: 1.4rem; /* Further reduce font size for smaller screens */
  }
  .company-description {
    font-size: 1.2rem; /* Further reduce font size for smaller screens */
  }
}
@media (max-width: 768px) {
  .experience-title-container {
    margin-top: 1.6rem; /* Adjust top margin for smaller screens */
  }
  h2 {
    font-size: 2rem; /* Further reduce font size for smaller screens */
  }
  .rectangle {
    height: 1.2rem; /* Adjust height for smaller screens */
  }
  .experience-container {
    padding: 0 1rem; /* Adjust padding for smaller screens */
    gap: 2rem; /* Adjust gap for smaller screens */
  }
  .company-logo {
    width: 5rem; /* Further adjust logo size for smaller screens */
    height: 5rem;
  }
  .company-name {
    font-size: 1.8rem; /* Further reduce font size for smaller screens */
  }
  .company-role {
    font-size: 1.4rem; /* Further reduce font size for smaller screens */
  }
  .company-duration {
    font-size: 1.2rem; /* Further reduce font size for smaller screens */
  }
  .company-description {
    font-size: 1rem; /* Further reduce font size for smaller screens */
  }
}
</style>