<template>
    <Header />
    <Hero :image-source="imageUrl" />
    <Contents :time-slots="timeSlots" />
    <div class="positionButton">
        <div class="submitButtonContainer">
            <div
                class="submitButton"
                @click="submitBooking"
            >
                <div class="buttonText">
                    Jetzt buchen
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Header from "./components/Header/Header.vue";
import Hero from "./components/Hero/Hero.vue";
import Contents from "./components/contents/contents.vue";
import mockResponse from './common/mockApi/data.js';

export default {
    name: "App",
    components: {
        Header,
        Hero,
        Contents,
    },
    data: () => mockResponse,
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 45px;
}

body {
  margin: 0;
}
</style>
