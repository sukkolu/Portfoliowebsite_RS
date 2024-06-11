<template>
  <div class="skills-section">
    <h3>My skills</h3>
    <div class="skill-container">
      <div class="skill-group spreadsheets">
        <h4>Spreadsheets</h4>
        <skill-icons>
          <template v-slot:logo><p>MSExcel</p></template>
          <img src="@/assets/Excel.svg" class="skill-icon" />
        </skill-icons>
        <skill-icons>
          <template v-slot:logo><p>GoogleSheets</p></template>
          <img src="@/assets/googlesheet.svg" class="skill-icon" />
        </skill-icons>
      </div>
      <div class="skill-group data-wrangling">
        <h4>Data Wrangling</h4>
        <skill-icons>
          <template v-slot:logo><p>NumPy</p></template>
          <img src="@/assets/numpy.svg" class="skill-icon" />
        </skill-icons>
        <skill-icons>
          <template v-slot:logo><p>Pandas</p></template>
          <img src="@/assets/Pandas.svg" class="skill-icon" />
        </skill-icons>
        <skill-icons>
          <template v-slot:logo><p>SQL</p></template>
          <img src="@/assets/sql-database-generic-svgrepo-com.svg" class="skill-icon" />
        </skill-icons>
      </div>
      <div class="skill-group data-visualization">
        <h4>Data Visualization</h4>
        <skill-icons>
          <template v-slot:logo><p>PowerBI</p></template>
          <img src="@/assets/PowerBI.svg" class="skill-icon" />
        </skill-icons>
        <skill-icons>
          <template v-slot:logo><p>Streamlit</p></template>
          <img src="@/assets/Streamlit.svg" class="skill-icon" />
        </skill-icons>
      </div>
      <div class="skill-group analytical-skills">
        <h4>Analytical Skills</h4>
        <skill-icons>
          <template v-slot:logo><p>Statistics</p></template>
          <img src="@/assets/statistics.svg" class="skill-icon" />
        </skill-icons>
        <skill-icons>
          <template v-slot:logo><p>Outlier</p></template>
          <img src="@/assets/outliers.svg" class="skill-icon" />
        </skill-icons>
      </div>
    </div>
    <div class="download-buttons">
      <base-button class="cv-button">
        <a href="https://drive.google.com/file/d/1BXzQ6dORq-pkkyzK1sMcFNfb62_dCx5Z/view?usp=drive_link" download target="_blank">
          Download CV
        </a>
      </base-button>
    </div>
  </div>
</template>

<script>
import SkillIcons from './SkillIcons.vue';

export default {
  components: {
    SkillIcons,
  },
};
</script>

<style scoped>
.skills-section {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.skills-section h3 {
  font-size: 9.6rem;
  color: #dee2e6;
  letter-spacing: 3px;
  text-shadow: 5px 5px #52b788;
  padding-right: 1.2rem;
  border-bottom: 3px solid #40916c;
  width: 110rem;
  text-align: center;
  margin-bottom: 3rem;
}

.skill-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 3rem;
}

.skill-group {
  display: flex;
  flex-direction: column;
  align-items: center;
}

h4 {
  font-size: 6.4rem;
  color: #dee2e6;
  letter-spacing: 3px;
  text-shadow: 5px 5px #52b788;
  padding-right: 1.2rem;
  text-align: center;
  margin-bottom: 1rem;
}

.skill-icon {
  width: 10.4em;
  height: 10.4em;
}

.cv-button {
  margin-top: 3rem;
}

@media (max-width: 768px) {
  .skills-section h3 {
    font-size: 6.4rem;
    width: 90%;
  }
  
  .skill-icon {
    width: 8em;
    height: 8em;
  }
}

@media (max-width: 576px) {
  .skills-section h3 {
    font-size: 4.8rem;
    width: 90%;
  }
  
  .skill-icon {
    width: 6em;
    height: 6em;
  }
}
</style>
