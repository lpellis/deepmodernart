<template>
  <section class="height-30  jarallax" style="background-color:#FBE8DA">


    <b-container>
      <b-row class="justify-content-center text-center">
        <b-col md="10" lg="8" class="pt-3 pb-3" style="overflow:hidden">
          <p class="display-4 mb-0">{{ record.title }}</p>
          <p class="leadx aboutlead" v-if="record.subtitle">{{ record.subtitle}}</p>
        </b-col>
      </b-row>
    </b-container>
  </section>
</template>

<script>
export default {
  props: ["record"]
};
</script>

