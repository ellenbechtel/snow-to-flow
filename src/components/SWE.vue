<template>
  <!---VizSection-->
  <VizSection id="firstSection">
    <!-- TAKEAWAY TITLE -->
    <template v-slot:takeAway>
      <h2>Timing and Magnitude of Peak SWE help cue scientists as to whether it's a "good" or "bad" snow year.</h2>
    </template>
    <!-- FIGURES -->
    <template v-slot:figures>
      <div class="group single maxWidth">
        <figure id="swe-chart-container">
          <!-- <img src="@/assets/diagrams/SWE-sketch.png"> -->
          <LineChart v-bind:class="[toggleClass]" />
          <button v-on:click="play">Play again</button>
        </figure>
      </div>
    </template>
    <!-- FIGURE CAPTION -->
    <template v-slot:figureCaption>
      <p>
        Figs. Wildfires affect the timing and magnitude of runoff and groundwater recharge.
      </p>
    </template>
    <!-- EXPLANATION -->
    <template v-slot:explanation>
      <p>Stuff to explain.</p>
    </template>
  </VizSection>
</template>
<script>

import VizSection from '@/components/VizSection';
import LineChart from '@/components/LineChart';
import text from "@/assets/text/sweText";
export default {
    name: "SWE",
    components:{
        LineChart,
        VizSection
    },
    data() {
      return {
        toggleClass: "animation1"
      };
    },
    methods: {
      play() {
        // toggle classes to animate the line draw
        this.toggleClass == "animation1"
          ? (this.toggleClass = "animation2")
          : (this.toggleClass = "animation1");
      }
    }
}
</script>
<style lang="scss" scoped>
  button { 
    background: gold;
    padding: 10px;
    border-radius: 5px;
  }

    // #swe-chart-container img {
    //   width: 100%;
    // }
</style>