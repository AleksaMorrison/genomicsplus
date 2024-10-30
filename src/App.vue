<script setup>
import HeaderNav from './components/HeaderNav.vue'
import TheSpace from './components/TheSpace.vue'
import TheInfoBlock from './components/TheInfoBlock.vue';
import TheFooter from './components/TheFooter.vue';
import { ref,onMounted,onUnmounted } from 'vue';

const isMobile = ref(false);

const checkScreen = () => {
  if (window.innerWidth <= 768) {
    isMobile.value = true;
  } else {
    isMobile.value = false;
  }
}

onMounted(() => {
  checkScreen();
  window.addEventListener('resize', checkScreen); 
});

onUnmounted(() => {
  window.removeEventListener('resize', checkScreen);
});
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
  <div class="fab" v-if="isMobile">
    <div class="fab-wrapper">
      <a href="#" class="cta-button">Contact Us</a>
    </div>
  </div>
</template>

<style scoped lang="scss">
.fab {
  position: fixed;
  bottom: 20px;
  z-index: 1000;
  display: flex;
  width: 100%;
  justify-content: center;
  align-items: center;

  & .fab-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: var(--dark-background);
    width: 200px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);

    & .cta-button {
      background: linear-gradient(to right,#ffc75f, #da7df0 ,#00d5e6 51%, #f9f871);
      background-clip: text;
      -webkit-text-fill-color: transparent;
      background-size: 200% 200%;
      color:var(--light-text);
      transition: color .2s ease-in-out;
      font-weight: 700;
      text-align: center;
      border-radius: 8px;
      border:  1px solid var(--light-text);
      width: 200px;
      align-self: center;
      font-size: 16px;
      padding: 5px 10px;
      transition: background 0.3s;
      animation: rainbow 2s ease-in-out infinite;

      &:hover {
        background: linear-gradient(to right, #f9f871,#00d5e6 51%,#da7df0, #ffc75f);
        background-clip: text;
        color: var(--dark-gray);
      }

      @media (min-width: 768) {
        font-size: 20px;
        padding: 10px 20px;
      }
    }
  }
}
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
