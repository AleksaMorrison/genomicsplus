<script setup>
import HeaderNav from './components/HeaderNav.vue'
import TheSpace from './components/TheSpace.vue'
import TheInfoBlock from './components/TheInfoBlock.vue';
import TheFooter from './components/TheFooter.vue';
</script>

<template>
  <header class="hero">
    <div class="overlay"></div>
    <div class="header-content">
      <HeaderNav/>
    </div>
    <TheSpace>
      <h1>AI Platform for Biomolecular Data</h1>
    </TheSpace>    
  </header>

  <main>
    <TheSpace>
      <TheInfoBlock/>
    </TheSpace>    
  </main>

  <footer>
    <TheSpace>
      <TheFooter/>
    </TheSpace>   
  </footer>
  
</template>

<style scoped lang="scss">
.hero {
  position: relative;
  display: flex;
  flex-direction: column;
  gap: 100px;
  background-image: url('/src/img/dna.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-color: var(--dark-background);
  box-shadow: inset 0px -99px 115px 50px #080707;

  & .overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
  }

  & .header-content {
    z-index: 1000;
    width: 100%;
    position: fixed;

    @media (min-width: 1024px) {
      top: 20px;
      padding: 0 130px;
    }
  }
  
  &:deep(.space) {
    z-index: 100;
    & h1 {
      color: var(--lighter-text);
      font-size: 32px;
      font-weight: 700;
      margin-top: 200px;
      text-align: center;
      @media (min-width: 1024px) {
        font-size: 40px;
      }
    }
  }
}
</style>
