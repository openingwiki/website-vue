<script setup>
</script>

<template>
  <header>
    <div class="site-name" @click="this.$router.push('/')">Opening.wiki</div>
    <nav class="navigation">
      <ul>
        <li><router-link to="/">Openings</router-link></li>
        <li><router-link to="/">Endings</router-link></li>
        <li><router-link to="/">Osts</router-link></li>
      </ul>
    </nav>
    <div class="auth-buttons">
      <NiceButton :class="nice-button" @click="this.$router.push('/login')">Login</NiceButton>
      <NiceButton :class="nice-button" @click="this.$router.push('/register')">Sign Up</NiceButton>
    </div>
  </header>
</template>

<script>
import NiceButton from "@/components/NiceButton.vue";

export default {
  name: "HeaderBar",
  components: {
    NiceButton,
  }
};
</script>

<style scoped>
header {
  padding-left: 10px;
  padding-right: 10px;
  background-color: #232341;
  display: flex;
  justify-content: space-between;  /* Ensures space between elements */
  align-items: center;  /* Vertically aligns all elements */
  height: 60px;
}

a {
  color: white;
  text-decoration: none;
}

.site-name {
  font-size: 24px;
  font-weight: bold;
  transition: transform 0.2s ease, color 0.2s ease;  /* Smooth transition for click effect */
  width: 220px;
}

.site-name:hover {
  color: #92a5b8;
}

.site-name:active {
  transform: scale(0.97);  /* Slightly scale down the site name on click to simulate a "pressed" effect */
  color: #8ab0d7;  /* Change the color on click */
}

.navigation {
  flex-grow: 1;  /* This makes the navigation take up available space */
  display: flex;
  justify-content: center;  /* Centers the navigation links */
  height: 100%;
}

.navigation ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;  /* Flex container for the navigation items */
  justify-content: center;  /* Horizontally center the list items */
  align-items: center;
}

.navigation li {
  width: 130px;
  align-items: center;
  display: flex;
  justify-content: center;
  height: 100%;
}

.navigation li:hover {
  background-color: #1E1E2E;  /* Change the background color to blue on hover */
}

.navigation a {
  text-decoration: none;  /* Remove the underline from links */
  color: white;  /* Default text color */
  font-size: 16px;
  transition: color 0.1s ease, transform 0.1s ease;  /* Smooth transition for color and transform */
  height: 100%;
  display: flex;
  align-items: center;
}

.navigation a:hover {
  transform: scale(1.05);  /* Slightly scale the text on hover */
}

.auth-buttons {
  display: flex;
  gap: 10px;  /* Space between the auth buttons */
  width: 220px;
}

/* Hover effect */
button:hover {
  background-color: #1565C0;
  transform: translateY(-1px);  /* Slightly lift the button */
}

/* Active effect */
button:active {
  transform: translateY(0);  /* Return to normal position on click */
  background-color: #0051aa;
}
</style>