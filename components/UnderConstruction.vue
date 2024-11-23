<script setup>
import { onMounted, ref } from "vue";

const typingText = ref(null);
const text = "Under Construction... Please Come Back Soon!";

onMounted(() => {
  let index = 0;
  const typingSpeed = 100; // Speed of typing in milliseconds

  function type() {
    if (index < text.length) {
      typingText.value.innerHTML += text.charAt(index);
      index++;
      setTimeout(type, typingSpeed);
    }
  }

  type();
});
</script>

<template>
  <div class="construction-container">
    <div class="construction-icon">
      <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="icon"
      >
        <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M3.375 19.5L9.75 7.875h4.5L20.625 19.5m-17.25 0h17.25M9.75 7.875L12 3m-2.25 4.875h4.5m-2.25 0L12 12"
        />
      </svg>
    </div>
    <div class="construction-text">
      <span ref="typingText" class="typed-text"></span>
      <span class="cursor">|</span>
    </div>
  </div>
</template>

<style scoped>
/* Main container */
.construction-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  background: linear-gradient(135deg, #f7f8fc, #e3e5f1);
  color: #2d3748;
  text-align: center;
  overflow: hidden;
}

/* Animated icon */
.construction-icon {
  margin-bottom: 2rem;
}

.icon {
  width: 100px;
  height: 100px;
  animation: bounce 1.5s infinite ease-in-out;
}

/* Bounce animation for icon */
@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

/* Typing effect */
.construction-text {
  font-size: 1.5rem;
  font-family: "Courier New", Courier, monospace;
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Blinking cursor */
.cursor {
  margin-left: 4px;
  font-size: 1.5rem;
  animation: blink 0.7s steps(2, start) infinite;
}

@keyframes blink {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: 0;
  }
}

/* Responsive */
@media (max-width: 768px) {
  .construction-text {
    font-size: 1.2rem;
  }

  .icon {
    width: 70px;
    height: 70px;
  }
}
</style>