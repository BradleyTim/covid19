<template>
  <div class="about">
    <div class="about-info">
      <h3>COVID-19</h3>
      <div>
        <p>The first case of the new Coronavirus COVID-19 was
        recorded on 31 December in Wuhan, China (WHO).
        Since then, many confirmed cases have been recorded worldwide.
        </p>
        <p>
          The Symptoms include fever, dry cough, sneezing,
           headache and difficulty breathing.
           They start within 14 days.
        </p>
        <p>This site shows and tracks the near real-time status based
        on data from the Center for Systems Science
        and Engineering (CSSE) at Johns Hopkins University.
        </p>
      </div>
    </div>
  </div>
</template>


<style scoped>
.about {
  width: 90%;
  margin: 0 auto;
}

.about-info {
  margin-top: 5rem;
  font-size: 1.25rem;
  border: 1px solid #eee;
  box-shadow: 3px 5px 0 0#eee;
  padding: 2rem;
}

h3 {
  font-weight: 800;
  text-align: center;
  margin-bottom: .5rem;
}

p {
  padding: .35rem 0;
}

@media screen and (max-width: 500px) {
  .about-info {
    margin-top: 2rem;
    font-size: 1.25rem;
    padding: 1rem;
    border: none;
    box-shadow: none;
    text-align: center;
  }
}
</style>
