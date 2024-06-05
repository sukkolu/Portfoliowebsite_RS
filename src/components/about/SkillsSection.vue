<template>
  <div class="skills-section">
    <h3>My skills</h3>
    <div class="skill-container">
      <div class="spreadsheets">
        <h4>Spreadsheets</h4>
        <SkillIcons>
          <template v-slot:logo><p>MSExcel</p></template>
          <img src="@/assets/Excel.svg" class="skill-icon" />
        </SkillIcons>
        <SkillIcons>
          <template v-slot:logo><p>GoogleSheets</p></template>
          <img src="@/assets/googlesheet.svg" class="skill-icon" />
        </SkillIcons>
      </div>
      <div class="data-wrangling">
        <h4>DataWrangling</h4>
        <SkillIcons>
          <template v-slot:logo><p>NumPy</p></template>
          <img src="@/assets/numpy.svg" class="skill-icon" />
        </SkillIcons>
        <SkillIcons>
          <template v-slot:logo><p>Pandas</p></template>
          <img src="@/assets/Pandas.svg" class="skill-icon" />
        </SkillIcons>
        <SkillIcons>
          <template v-slot:logo><p>SQL</p></template>
          <img src="@/assets/sql-database-generic-svgrepo-com.svg" class="skill-icon" />
        </SkillIcons>
      </div>
      <div class="data-visualization">
        <h4>DataVisualization</h4>
        <SkillIcons>
          <template v-slot:logo><p>PowerBI</p></template>
          <img src="@/assets/PowerBI.svg" class="skill-icon" />
        </SkillIcons>
        <SkillIcons>
          <template v-slot:logo><p>Streamlit</p></template>
          <img src="@/assets/Streamlit.svg" class="skill-icon" />
        </SkillIcons>
      </div>
      <div class="analytical-skills">
        <h4>AnalyticalSkills</h4>
        <SkillIcons>
          <template v-slot:logo><p>Statistics</p></template>
          <img src="@/assets/statistics.svg" class="skill-icon" />
        </SkillIcons>
        <SkillIcons>
          <template v-slot:logo><p>Outlier</p></template>
          <img src="@/assets/outliers.svg" class="skill-icon" />
        </SkillIcons>
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
import SkillIcons from './SkillIcons.vue'

export default {
  components: {
    SkillIcons,
  }
}
</script>

<style scoped>
.skills-section {
  display: grid;
  grid-template-rows: auto auto auto;
  justify-items: center;
}
.socket {
  width: auto;
  height: auto;
}

.skills-section h3 {
  font-size: 4rem;
  color: #dee2e6;
  letter-spacing: 3px;
  text-shadow: 5px 5px #52b788;
  padding-right: 1.2rem;
  border-bottom: 3px solid #40916c;
  text-align: center;
  margin-bottom: 1rem;
}

.download-buttons {
  margin-top: 2.4rem;
  display: flex;
  gap: 2.4rem;
}

.spreadsheets,
.data-wrangling,
.data-visualization,
.analytical-skills {
  display: grid;
  place-items: center;
  gap: 1.6rem;
}

.skill-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 2rem;
  width: 100%;
  padding: 1rem;
}

.skill-icon {
  width: 5rem;
  height: 5rem;
}

h4 {
  font-size: 2rem;
  color: #dee2e6;
  letter-spacing: 3px;
  text-shadow: 5px 5px #52b788;
  padding-right: 1.2rem;
  text-align: center;
  margin: 0;
}

.cv-button {
  margin-bottom: 4rem;
}

@media (max-width: 1220px) {
  .skill-icon {
    width: 4.5rem;
    height: 4.5rem;
  }
}

@media (max-width: 992px) {
  .skills-section h3 {
    font-size: 3.2rem;
  }
  h4 {
    font-size: 1.8rem;
  }
  .skill-icon {
    width: 4rem;
    height: 4rem;
  }
}

@media (max-width: 768px) {
  .skills-section h3 {
    font-size: 2.8rem;
  }
  h4 {
    font-size: 1.6rem;
  }
  .skill-icon {
    width: 3.5rem;
    height: 3.5rem;
  }
}

@media (max-width: 576px) {
  .skills-section h3 {
    font-size: 2.4rem;
  }
  h4 {
    font-size: 1.4rem;
  }
  .skill-icon {
    width: 3rem;
    height: 3rem;
  }
}
</style>
