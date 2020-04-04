<template>
  <DefaultLayout>
    <SectionHeaderBanner></SectionHeaderBanner>

    <section class="pt-5">
      <b-container>


        <div>
          <b-row>
            <b-col class="py-2" md="3" lg="3" sm="3">
              <b-card class="h-100" footer-class="border-0 " style="text-align:center;border:1px solid #F8F9FC;border-radius:2px;background-color:#F8F9FC">

              <h3>Abstract Art</h3>

                <b-card-text>
               <img src="/images/home/abstract.jpg" style="width:100%">
                </b-card-text>
                <b-card-text>
                  <g-link class="card-link" :to="recordLink">Continue reading...</g-link>
                </b-card-text>
              </b-card>
            </b-col>
            <b-col class="py-2" md="1" lg="1" sm="1">
                <div style="text-align:center;height:100%">+</div>
            </b-col>

            <b-col class="py-2" md="3" lg="3" sm="3">
              <b-card class="h-100" footer-class="border-0 " style="border:1px solid #F8F9FC;border-radius:2px;background-color:#F8F9FC">

                 <h3>DeepDream</h3>

                <b-card-text>
                  <img src="/images/home/deepdream.png" style="width:100%">
                </b-card-text>
                <b-card-text>
                  <g-link class="card-link" :to="recordLink">Continue reading...</g-link>
                </b-card-text>
              </b-card>
            </b-col>

            <b-col class="py-2" md="1" lg="1" sm="1">
              <div style="text-align:center;height:100%">=</div>
            </b-col>

            <b-col class="py-2" md="3" lg="3" sm="3">
              <b-card class="h-100" footer-class="border-0 " style="border:1px solid #F8F9FC;border-radius:2px;background-color:#F8F9FC">

                 <h3>DeepAbstract</h3>

                <b-card-text>
                  <img src="/images/home/deepabstract.jpg" style="width:100%">
                </b-card-text>
                <b-card-text>
                  <g-link class="card-link" :to="recordLink">Continue reading...</g-link>
                </b-card-text>
              </b-card>
            </b-col>
          </b-row>

        </div>
      </b-container>
    </section>

    <SectionLatestArticles></SectionLatestArticles>

    <SectionContribute></SectionContribute>

    <SectionInfoBoxes></SectionInfoBoxes>

    <SectionLatestNews></SectionLatestNews>

    <SectionOpenSource></SectionOpenSource>

  </DefaultLayout>
</template>

<script>
import SectionHeaderBanner from "~/layouts/sections/index/HeaderBanner.vue";
import SectionLatestArticles from "~/layouts/sections/index/LatestArticles.vue";
import SectionLatestNews from "~/layouts/sections/index/LatestNews.vue";

import SectionContribute from "~/layouts/sections/index/Contribute.vue";
import SectionInfoBoxes from "~/layouts/sections/index/InfoBoxes.vue";
import SectionOpenSource from "~/layouts/sections/index/OpenSource.vue";

export default {
  components: {
    SectionHeaderBanner,
    SectionLatestArticles,
    SectionLatestNews,
    SectionContribute,
    SectionInfoBoxes,
    SectionOpenSource
  },
  metaInfo: {
    title: "DeepDream Abstract Art"
  }
};
</script>

