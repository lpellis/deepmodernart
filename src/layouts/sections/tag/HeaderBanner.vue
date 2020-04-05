<template>
  <section class="height-30 bg-dark text-white jarallax">
    <g-image
            src="~/resources/images/freddy.jpg"
            class="jarallax-img opacity-20"
            alt="Articles"
    />
    <b-container>
      <b-row class="justify-content-center text-center">
        <b-col md="10" lg="8" class="pt-3 pb-3">
          <p class="display-4 mb-0">{{tag}}</p>
          <p class="lead">{{ totalCount }} pieces</p>
        </b-col>


      </b-row>
    </b-container>
  </section>
</template>

<script>
export default {
  props: [
    'totalCount',
    'tag'
  ]
}
</script>

