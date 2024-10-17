<template>
  <v-app>
    <v-main>
      <!-- Cover / Landing Page (HelloWorld) -->
      <section id="cover" class="section fill-height">
        <HelloWorld @scroll-to-section="scrollToSection" />
      </section>

      <!-- Group Members Section -->
      <section id="group-members" class="section fill-height">
        <GroupMembers />
      </section>

      <!-- Assignment 1 Section -->
      <section
        id="assignment-1"
        class="section fill-height"
        style="background-color: #121212"
      >
        <Assignment
          :assignmentNumber="1"
          pdfLink="CISC332_A1.pdf"
          presentationLink="https://youtu.be/8MGcWPZLck0"
        />
      </section>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import GroupMembers from "./components/GroupMembers.vue";
import Assignment from "./components/Assignment.vue";
import { useGoTo } from "vuetify";

export default {
  components: {
    HelloWorld,
    GroupMembers,
    Assignment,
  },
  setup() {
    const goTo = useGoTo();

    // Programmatically scroll to a specific section
    const scrollToSection = (sectionId) => {
      goTo(`#${sectionId}`, {
        duration: 500, // Scroll duration in ms
        easing: "easeInOutCubic", // Easing function for smooth scroll
      });
    };

    return {
      scrollToSection,
    };
  },
};
</script>

<style scoped>
.fill-height {
  min-height: 20vh;
}

.section {
  scroll-snap-align: start;
  scroll-snap-stop: always;
}

v-main {
  scroll-snap-type: y mandatory;
  overflow-y: scroll;
}
</style>
