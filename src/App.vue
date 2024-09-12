<template>
  <v-app>
    <v-main>
        <!-- Cover / Landing Page (HelloWorld) -->
        <section id="cover" class="section fill-height">
          <HelloWorld @scroll-to-group="scrollToGroupMembers"/>
        </section>

        <!-- Group Members Section -->
        <section id="group-members" class="section fill-height">
          <GroupMembers />
        </section>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import GroupMembers from './components/GroupMembers.vue';
import { useGoTo } from 'vuetify'

export default {
  components: {
    HelloWorld,
    GroupMembers,
  },
  setup() {
    const goTo = useGoTo();

    // Programmatically scroll to the Group Members section
    const scrollToGroupMembers = () => {
      goTo('#group-members', {
        duration: 500, // Scroll duration in ms
        easing: 'easeInOutCubic' // Easing function for smooth scroll
      });
    };

    return {
      scrollToGroupMembers
    };
  }
};
</script>

<style scoped>
.fill-height {
  min-height: 50vh;
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
