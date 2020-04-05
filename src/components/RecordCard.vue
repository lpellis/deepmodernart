<template>

    <b-col class="py-2" md="6" lg="4" sm="6">


      <b-card class="h-100 infobox" footer-class="border-0">

          <b-card-title tag="h4">
            {{ record.title }}
          </b-card-title>


        <b-card-text>
          <g-link class="card-link" :to="recordLink"><img  :src="`/images/art/${record.image}/deepart.jpg`" style="max-width:100%;max-height:280px"></g-link>
          <br>
          {{ record.author }}
        </b-card-text>

      </b-card>

    </b-col>

</template>

<script>

export default {
  components: {
  },
  props: ['record'],
  computed: {
    recordLink() {
      if( this.record.recordType == 'Article') {
        return `/articles/${this.record.slug}`;
      }
      if( this.record.recordType == 'News') {
        return `/news/${this.record.slug}`;
      }

      return this.record.path;
    }
  }
}
</script>
<style lang="scss">
  .infobox{
    border:1px solid #eff0f3;
    border-radius:2px;
    background-color:#F8F9FC;
    text-align:center;
  }
</style>
