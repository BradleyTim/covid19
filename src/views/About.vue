<template>
  <div class="about">
    <div class="about-info">
      <h3>COVID-19</h3>
      <span>
        The first case of the new Coronavirus COVID-19 was
      </span>
      <span>
        recorded on 31 December in Wuhan, China (WHO).
      </span>
      <span>
        Since then, many confirmed cases have been recorded worldwide.
      </span>
      <span>
        This site shows and tracks the near real-time status based
      </span>
      <span>
        on data from the Center for Systems Science
      </span>
      <span>
        and Engineering (CSSE) at Johns Hopkins University and DXY.
      </span>
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
  font-weight: 300;
  text-align: center;
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
