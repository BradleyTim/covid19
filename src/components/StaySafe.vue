<template>
  <section class="informational">
    <h3>Stay Safe</h3>
    <div class="info-container">
      <p class="bg-default">
      Wash your hands regulary with soap and running water or use an alcohol based hand
       sanitizer.
      </p>
      <p class="bg-default">
        Cough or sneeze into a disposable tissue or bent elbow, and
        wash hands immediately. Dispose the tissue in atrash or burn it.
      </p>
      <p class="bg-default">
        Avoid shaking hands, hugging or kissing with people with flu-like symptoms
      </p>
      <p class="bg-default">
        Stay at home and avoid travelling when you have flu-like symptoms.
      </p>
    </div>
  </section>
</template>


<script>
export default {
  name: 'StaySafe',
};
</script>

<style scoped>
.informational {
  width: 100%;
  /* margin-top: 1rem; */
}

h3 {
  text-align: center;
  font-weight: 300;
  font-size: 1.25rem;
  margin-bottom: 1rem;
}

p {
  padding: .5rem 0;
  font-size: .85rem;
  text-align: center;
  letter-spacing: 1px;

  border: .5px solid #eee;
  border-radius: 3px;
  margin: .75rem 0;
  padding: .75rem;
}

@media screen and (min-width: 860px) {

  .info-container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 1rem;
  }

  h3 {
    text-align: center;
    font-weight: 300;
    font-size: 1.5rem;
    margin-bottom: 1rem;
  }

  p {
    padding: 1rem;
  }
}
</style>
