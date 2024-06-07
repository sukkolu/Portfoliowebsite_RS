<template>
  <div class="skills-section">
    <h3>My skills</h3>
    <div class="skill-container">
      <div class="spreadsheets">
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
      <div class="data-wrangling">
        <h4>DataWrangling</h4>
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
      <div class="data-visualization">
        <h4>DataVisualization</h4>
        <skill-icons>
          <template v-slot:logo><p>PowerBI</p></template>
          <img src="@/assets/PowerBI.svg" class="skill-icon" />
        </skill-icons>
        <skill-icons>
          <template v-slot:logo><p>Streamlit</p></template>
          <img src="@/assets/Streamlit.svg" class="skill-icon" />
        </skill-icons>
      </div>
      <div class="analytical-skills">
        <h4>AnalyticalSkills</h4>
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
import SkillIcons from './SkillIcons.vue'
import BaseButton from '../UI/BaseButton.vue'

export default {
  components: {
    SkillIcons,
    BaseButton,
  }
}
</script>

<style scoped>
.skills-section {
  display: grid;
  grid-template-rows: 1fr 2fr 0.5fr;
  justify-items: center;
}
.socket {
  width: auto;
  height: auto;
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
  row-gap: 5.6rem;
  column-gap: 2.8rem;
}

.spreadsheets {
  grid-template-rows: 1fr 1fr 1fr;
  grid-template-columns: 12rem 12rem;
}

.data-wrangling {
  grid-template-rows: 1fr 1fr 1fr;
  grid-template-columns: 12rem 12rem 12rem;
}

.data-visualization {
  grid-template-rows: 1fr 1fr 1fr;
  grid-template-columns: 12rem 12rem;
}

.analytical-skills {
  grid-template-columns: 12rem 12rem;
  grid-column: 1/-1;
}

h4 {
  font-size: 3.4rem;
  color: #dee2e6;
  letter-spacing: 3px;
  text-shadow: 5px 5px #52b788;
  padding-right: 1.2rem;
  width: 110rem;
  text-align: center;
  grid-column: 1/-1;
  padding: 0 1rem;
}
.skill-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 1fr 1fr;
  column-gap: 8em;
  height: 27.5rem;
  place-items: center;
  align-items: start;
}
.skill-icon {
  width: 10.4em;
  height: 10.4em;
}
.cv-button {
  margin-bottom: 9.6rem;
}

@media (max-width: 1220px) {
  .skill-icon {
    width: 8.2em;
    height: 8.2em;
  }
  .spreadsheets {
    grid-template-columns: 9.6rem 9.6rem;
  }

  .data-wrangling {
    grid-template-columns: 9.6rem 9.6rem 9.6rem;
  }

  .data-visualization {
    grid-template-columns: 9.6rem 9.6rem;
  }

  .spreadsheets,
  .data-wrangling,
  .data-visualization {
    row-gap: 3.4rem;
    column-gap: 2.4rem;
  }

  .skill-container {
    column-gap: 5.5em;
  }
  .skills-section {
    grid-template-rows: 0.7fr 1.5fr 0.2fr;
  }
}

@media (max-width: 1140px) {
  .skills-section h3 {
    font-size: 8.2rem;
    width: 92rem;
  }
  h4 {
    font-size: 3.4rem;
  }
  .analytical-skills {
    grid-template-columns: 9.6rem 9.6rem;
  }

  .skill-icon {
    width: 6.4em;
    height: 6.4em;
  }
  .spreadsheets {
    grid-template-columns: 8.2rem 8.2rem;
  }

  .data-wrangling {
    grid-template-columns: 8.2rem 8.2rem 8.2rem;
  }
  .spreadsheets,
  .data-wrangling,
  .data-visualization {
    row-gap: 3.2rem;
    column-gap: 1.2rem;
  }

  .skill-container {
    column-gap: 5.5em;
  }
  .data-visualization {
    grid-template-columns: 8.2rem 8.2rem;
  }
  .skills-section {
    grid-template-rows: 0.5fr 1fr 0.2fr;
  }
}

@media (max-width: 992px) {
  .skills-section h3 {
    font-size: 6.4rem;
    width: 78rem;
  }
  h4 {
    font-size: 3.4rem;
  }
  .analytical-skills {
    grid-template-columns: 6.4rem 6.4rem;
  }
  .skill-icon {
    width: 4.8em;
    height: 4.8em;
  }
  .spreadsheets {
    grid-template-columns:6.4rem 6.4rem;
  }

  .data-wrangling {
    grid-template-columns: 6.4rem 6.4rem;
  }
  .spreadsheets,
  .data-visualization,
  .data-wrangling {
    row-gap: 2.2rem;
    column-gap: 1rem;
  }

  .skill-container {
    column-gap: 4.8em;
  }
  .data-visualization {
    grid-template-columns: 6.4rem 6.4rem;
  }
  .skills-section {
    grid-template-rows: 0.5fr 1fr 0.2fr;
  }

  .cv-button {
    margin-bottom: 4.8rem;
  }
}

@media (max-width: 768px) {
  .skills-section h3 {
    font-size: 4.8rem;
    width: 58rem;
  }
  h4 {
    font-size: 3rem;
  }
  .analytical-skills {
    grid-template-columns: 4.8rem 4.8rem;
  }
  .skill-icon {
    width: 4em;
    height: 4em;
  }
  .spreadsheets {
    grid-template-columns: 4.8rem 4.8rem;
  }

  .data-wrangling {
    grid-template-columns: 4.8rem 4.8rem;
  }
  .spreadsheets,
  .data-visualization,
  .data-wrangling {
    row-gap: 2.2rem;
    column-gap: 1rem;
  }

  .skill-container {
    height: 22.5rem;
    column-gap: 3.2em;
  }
  .data-visualization {
    grid-template-columns: 4.8rem 4.8rem;
  }
  .skills-section {
    grid-template-rows: 0.3fr 1fr 0.1fr;
  }

  .cv-button {
    margin-bottom: 4.8rem;
  }
}

@media (max-width: 580px) {
  .skills-section h3 {
    font-size: 3.2rem;
    width: 40rem;
    text-shadow: 4px 4px #52b788;
  }
  h4 {
    text-shadow: 2.5px 2.5px #52b788;
    font-size: 2rem;
  }
  .analytical-skills {
    grid-template-columns: 4rem 4rem;
  }
  .skill-icon {
    width: 3.2em;
    height: 3.2em;
  }
  .spreadsheets {
    grid-template-columns: 4rem 4rem 4rem;
  }

  .data-wrangling {
    grid-template-columns: 4rem 4rem;
  }
  .spreadsheets,
  .data-visualization,
  .data-visualization {
    row-gap: 2.2rem;
    column-gap: 1rem;
  }

  .skill-container {
    height: 18rem;
    column-gap: 3em;
  }
  .data-visualization {
    grid-template-columns: 4.8rem 4.8rem;
  }
  .skills-section {
    grid-template-rows: 0.2fr 0.6fr 0.1fr;
  }

  .cv-button {
    margin-bottom: 3.2rem;
  }
}

@media (max-width: 480px) {
  .skills-section h3 {
    font-size: 2.4rem;
    width: 33.5rem;
    text-shadow: 3px 3px #52b788;
  }
  h4 {
    text-shadow: 2px 2px #52b788;
    font-size: 1.6rem;
  }
  .skill-icon {
    width: 3.2em;
    height: 3.2em;
  }
  .spreadsheets {
    grid-template-columns: 3.2rem 3.2rem 3.2rem;
  }

  .data-wrangling {
    grid-template-columns: 3.2rem 3.2rem;
  }
  .spreadsheets,
  .data-visualization,
  .data-wrangling {
    row-gap: 1.6rem;
    column-gap: 1rem;
  }

  .skill-container {
    height: 15rem;
    column-gap: 3em;
  }
  .data-visualization {
    grid-template-columns: 3.6rem 3.6rem;
  }
  .skills-section {
    grid-template-rows: 0.2fr 0.6fr 0.1fr;
  }

  .cv-button {
    margin-bottom: 2.4rem;
  }
}

@media (max-width: 350px) {
  .skills-section h3 {
    font-size: 2rem;
    width: 25rem;
    text-shadow: 2px 2px #52b788;
  }
  h4 {
    text-shadow: 1px 1px #52b788;
    font-size: 1.2rem;
  }
  .analytical-skills {
    grid-template-columns: 2.4rem 2.4rem;
  }
  .skill-icon {
    width: 2.4em;
    height: 2.4em;
  }
  .spreadsheets {
    grid-template-columns: 2.4rem 2.4rem;
  }

  .data-wrangling {
    grid-template-columns: 2.4rem 2.4rem;
  }
  .spreadsheets,
  .data-visualization,
  .data-wrangling {
    row-gap: 1.2rem;
    column-gap: 0.4rem;
  }

  .skill-container {
    height: 12rem;
    column-gap: 3em;
  }
  .data-visualization {
    grid-template-columns: 3rem 3rem;
  }
  .skills-section {
    grid-template-rows: 0.2fr 0.5fr 0.1fr;
  }

  .cv-button {
    margin-bottom: 1.2rem;
  }
}
</style>
