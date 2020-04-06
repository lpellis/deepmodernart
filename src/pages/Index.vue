<template>
  <DefaultLayout>
    <SectionHeaderBanner></SectionHeaderBanner>

    <section class="pt-5">
      <b-container>


        <div>
          <b-row>
            <b-col class="py-2" md="3" lg="3" sm="3">
              <b-card class="h-100 infobox" footer-class="border-0 ">

              <h3>Abstract Art</h3>

                <b-card-text>
               <img src="/images/home/abstract.jpg" style="width:100%">
                </b-card-text>
              </b-card>
            </b-col>
            <b-col class="py-2" md="1" lg="1" sm="1">
                <div style="text-align:center;height:100%;position:absolute;top:40%;font-size:40px;left:30%">+</div>
            </b-col>

            <b-col class="py-2" md="3" lg="3" sm="3">
              <b-card class="h-100 infobox" footer-class="border-0 ">

                 <h3>DeepDream</h3>

                <b-card-text>
                  <img src="/images/home/deepdream.png" style="width:100%">
                </b-card-text>
              </b-card>
            </b-col>

            <b-col class="py-2" md="1" lg="1" sm="1">
              <div style="text-align:center;height:100%;position:absolute;top:40%;font-size:40px;left:30%">=</div>
            </b-col>

            <b-col class="py-2" md="3" lg="3" sm="3">
              <b-card class="h-100 infobox" footer-class="border-0 ">

                 <h3>DeepAbstract</h3>

                <b-card-text>
                  <img src="/images/home/deepabstract.jpg" style="width:100%">
                </b-card-text>
              </b-card>
            </b-col>
          </b-row>

        </div>
      </b-container>
    </section>
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
  },
  metaInfo: {
    title: "DeepDream Abstract Art"
  }
};
</script>
<style lang="scss">
  .infobox{
    border:1px solid #eff0f3;
    border-radius:2px;
    background-color:#F8F9FC
  }
</style>
