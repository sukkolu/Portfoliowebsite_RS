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
      <div class="data-visualization">
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
      <div class="analytical-skills">
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
  display: grid;
  grid-template-rows: auto auto auto;
  justify-items: center;
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
  grid-template-columns: repeat(2, 14rem);
}

.data-wrangling {
  grid-template-columns: repeat(3, 14rem);
}

.data-visualization {
  grid-template-columns: repeat(2, 14rem);
}

.analytical-skills {
  grid-template-columns: repeat(2, 14rem);
}

h4 {
  font-size: 6.4rem;
  color: #dee2e6;
  letter-spacing: 3px;
  text-shadow: 5px 5px #52b788;
  padding-right: 1.2rem;
  text-align: center;
  grid-column: 1/-1;
  padding: 0 1rem;
  margin-bottom: 1rem;
}

.skill-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: repeat(2, 1fr);
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
  .spreadsheets,
  .data-visualization {
    grid-template-columns: repeat(2, 10.4rem);
  }
  .data-wrangling {
    grid-template-columns: repeat(3, 9.6rem);
  }
  .analytical-skills {
    grid-template-columns: repeat(2, 10rem);
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
    grid-template-rows: auto auto auto;
  }
}

@media (max-width: 1140px) {
  .skills-section h3 {
    font-size: 8.2rem;
    width: 92rem;
  }
  h4 {
    font-size: 4.8rem;
  }
  .analytical-skills {
    grid-template-columns: repeat(2, 10rem);
  }
  .skill-icon {
    width: 6.4em;
    height: 6.4em;
  }
  .spreadsheets {
    grid-template-columns: repeat(2, 8.2rem);
  }
  .data-wrangling {
    grid-template-columns: repeat(3, 9.6rem);
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
    grid-template-columns: repeat(2, 9.6rem);
  }
}

@media (max-width: 800px) {
  .skills-section h3 {
    font-size: 5.8rem;
    width: 78rem;
  }
  h4 {
    font-size: 3.2rem;
  }
  .analytical-skills {
    grid-template-columns: repeat(2, 7.6rem);
  }
  .spreadsheets {
    grid-template-columns: repeat(2, 7.6rem);
  }
  .skill-icon {
    width: 5.8em;
    height: 5.8em;
  }
  .data-wrangling {
    grid-template-columns: repeat(3, 7.2rem);
  }
  .spreadsheets,
  .data-wrangling,
  .data-visualization {
    row-gap: 1.6rem;
    column-gap: 0.8rem;
  }
  .skill-container {
    column-gap: 5.5em;
  }
  .data-visualization {
    grid-template-columns: repeat(2, 7.2rem);
  }
}

@media (max-width: 600px) {
  .skills-section h3 {
    font-size: 4.8rem;
    width: 70rem;
  }
  h4 {
    font-size: 2.8rem;
  }
  .analytical-skills {
    grid-template-columns: repeat(2, 6rem);
  }
  .spreadsheets {
    grid-template-columns: repeat(2, 6rem);
  }
  .skill-icon {
    width: 5.4em;
    height: 5.4em;
  }
  .data-wrangling {
    grid-template-columns: repeat(3, 5.6rem);
  }
  .spreadsheets,
  .data-wrangling,
  .data-visualization {
    row-gap: 1.4rem;
    column-gap: 0.6rem;
  }
  .skill-container {
    column-gap: 5.5em;
  }
  .data-visualization {
    grid-template-columns: repeat(2, 5.6rem);
  }
}

</style>
