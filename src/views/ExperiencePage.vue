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
}
.experience-title-container {
  margin-top: 2.4rem;
  position: relative;
  grid-column: 1/-1;
  text-align: center;
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
  width: 90%;
  top: 10%;
  height: 2rem;
  border-left: 5px solid #40916c;
  animation: moveRect 1s 1 cubic-bezier(0.175, 0.885, 0.32, 1) forwards;
  overflow-x: auto; /* Enable horizontal scrolling */
}
@keyframes moveRect {
  0% {
    left: 50%;
  }
  100% {
    left: 100%;
    width: 1%;
  }
}
.experience-container {
  grid-column: 1/-1;
  display: flex;
  flex-direction: column;
  gap: 3.2rem;
  overflow-x: auto; /* Enable horizontal scrolling */
}
.company-logo {
  width: 8rem;
  height: 8rem;
  border-radius: 50%;
  border: 5px solid #40916c;
}
.company-details {
  display: flex;
  flex-direction: column;
}
.company-name {
  font-size: 3rem;
  color: #52b788;
}
.company-role {
  font-size: 2.4rem;
}
.company-duration {
  font-size: 2rem;
  color: #a9a9a9;
}
.company-description {
  font-size: 1.8rem;
  margin-top: 1rem;
}
@media (max-width: 992px) {
  h2 {
    font-size: 2.4rem;
  }
  .rectangle {
    height: 1.5rem;
  }
  .company-logo {
    width: 6rem;
    height: 6rem;
  }
  .company-name {
    font-size: 2.4rem;
  }
  .company-role {
    font-size: 2rem;
  }
  .company-duration {
    font-size: 1.6rem;
  }
  .company-description {
    font-size: 1.4rem;
  }
}
@media (max-width: 576px) {
  h2 {
    font-size: 1.8rem;
  }
  .rectangle {
    height: 1.2rem;
  }
  .company-logo {
    width: 4rem;
    height: 4rem;
  }
  .company-name {
    font-size: 1.8rem;
  }
  .company-role {
    font-size: 1.6rem;
  }
  .company-duration {
    font-size: 1.4rem;
  }
  .company-description {
    font-size: 1.2rem;
  }
}
</style>