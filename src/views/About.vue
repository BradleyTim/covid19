<template>
  <div class="about">
    <div class="about-info">
      <h3>COVID-19</h3>
      <div>
        The first case of the new Coronavirus COVID-19 was
        recorded on 31 December in Wuhan, China (WHO).
        Since then, many confirmed cases have been recorded worldwide.
        This site shows and tracks the near real-time status based
        on data from the Center for Systems Science
        and Engineering (CSSE) at Johns Hopkins University.
      </div>
    </div>
  </div>
</template>


<style scoped>
.about {
  width: 90%;
  min-height: 100%;
  margin: 0 auto;
}

.about-info {
  margin-top: 10rem;
  font-size: 1.25rem;
  border: 1px solid #eee;
  box-shadow: 3px 5px 0 0#eee;
  padding: 2rem;
}

h3 {
  font-weight: 300;
  text-align: center;
  margin-bottom: 1rem;
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
