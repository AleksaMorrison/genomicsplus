<script setup>
defineProps({
})
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
  <nav class="navigation">
    <ul class="nav-list">
      <li class="logo">
        <a href="#">Genomics+Ai</a>
      </li>
      <li v-if="!isMobile">
        <a class="contact" href="https://docs.google.com/forms/d/e/1FAIpQLSdg4_FNukpilJZq68jm9BBjHbPEcm7iQPlfUU31xdcfk7WIUQ/viewform" target="_blank" rel="noopener noreferrer">Contact Us</a>
      </li>
    </ul>
  </nav>
</template>

<style scoped lang="scss">
.navigation {
  height: 100px;
  padding: 10px 16px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  backdrop-filter: blur(15px);
  border: 1px solid var(--dark-gray);

  @media (min-width: 768px) {
    border-radius: 50px;
    padding: 10px 30px;
    border: 1px solid var(--dark-gray);
  }

  & .nav-list {
    list-style-type: none;
    display: flex;
    justify-content: flex-start;
    width: 100%;
    align-items: center;
    gap: 20px;
    

    & a {
      color: var(--light-text);

      &:hover {
        color: var(--lighter-text);
      }

      @media (min-width: 768px) {
        padding: 10px 20px;
      }

      &.contact {
        position: relative;
        background: linear-gradient(to right,#ffc75f, #da7df0 ,#00d5e6 51%, #f9f871);
        background-clip: text;
        -webkit-text-fill-color: transparent;
        background-size: 200% 200%;
        animation: rainbow 2s ease-in-out infinite;
        color:var(--light-text);
        transition: color .2s ease-in-out;

        &:hover {
          color:rgba(0,0,0,0);
        }

        &::before {
          content: '';
          position: absolute;
          right: 5px;
          top: 16px;
          border: solid var(--lighter-text);
          border-width: 0 2px 2px 0;
          display: inline-block;
          padding: 3px;
          transform: rotate(-45deg);
          -webkit-transform: rotate(-45deg);
          transition: right ease-in-out 0.3s;

          &:hover {
            right: 0;
          }
        }
      }
    }

    & .logo {
      flex-grow: 1;
      display: flex;
      justify-content: center;
      background: linear-gradient(to right,#ffc75f, #da7df0 ,#00d5e6 51%, #f9f871);
      background-clip: text;
      -webkit-text-fill-color: transparent;
      transition: background 0.3s;
      background-size: 200% 200%;
      animation: rainbow 2s ease-in-out infinite;
      
      @media (min-width: 768px) {
        justify-content: flex-start;
      }

      &:hover {
        background: linear-gradient(90deg #00d5e6 51%, #f9f871);
        -webkit-text-fill-color: transparent;
      }

      & a {
        color: var(--lighter-text);
        background: none;
        font-weight: 500;
        font-size: 32px;
        @media (min-width: 768px) {
          font-size: 40px;
        }
      }
    }
  }
}
</style>
