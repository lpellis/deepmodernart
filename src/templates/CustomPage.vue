<template>
  <DefaultLayout>

    <SectionHeaderBanner :record="$page.entry"></SectionHeaderBanner>

    <section class="pt-5 mb-5 page">
      <b-container>
        <b-row v-if="!showSidebar">
          <b-col>
            <div v-html="$page.entry.content" />
          </b-col>
        </b-row>

        <b-row v-if="showSidebar">
          <div class="container">
          <div class="row">
            <div class="col-8">
              <div v-html="$page.entry.content" />
              Follow us on Twitter:<br>
              <a href="https://twitter.com/deepabstractart" target="_blank" rel="noopener" style="padding:0;color:blue">
                <font-awesome :icon="['fab', 'twitter']"></font-awesome>
              </a>
            </div>
            <div class="col-4 sidebar">
              <SectionSidebar :record="$page.entry"></SectionSidebar>
            </div>

          </div>

          </div>
        </b-row>
      </b-container>
    </section>
  </DefaultLayout>
</template>

<page-query>
  query ($id: ID!) {
    entry : customPage(id: $id) {
      title
      subtitle
      image
      content
      sidebar
      headings {
        depth,
        value,
        anchor
      },
    }
  }
</page-query>

<script>
import SectionHeaderBanner from '~/layouts/sections/customPage/HeaderBanner.vue';
import SectionSidebar from "~/layouts/sections/customPage/Sidebar.vue";

export default {
  components : {
    SectionHeaderBanner,
    SectionSidebar
  },
  computed:{
    showSidebar() {
      return (this.$page.entry.sidebar) ? true : false;
    }
  },
  metaInfo() {
    return {
      title: this.$page.entry.title,
    }
  }
}
</script>

<style lang="scss">
  .page h3{
    font-size:120%;
  }
  .page p{
    font-size:90%;
  }
  .sidebar li{
    padding:10px;
    a {
      font-size: 11px;
    }
  }
</style>
