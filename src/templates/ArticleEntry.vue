<template>
  <DefaultLayout>
    <section class="height-60" style="background-color:#F8F9FD;">
      <b-container>
        <b-row class="justify-content-center text-center">
          <b-col md="8" lg="8" class="pt-3 pb-3">

            <img v-if="!showOriginal" :src="`/images/art/${$page.entry.image}/deepart.jpg`" style="max-width:100%;max-height:480px">
            <div v-if="showOriginal" style="font-size:80%">
            <img  :src="`/images/art/${$page.entry.image}/original.jpg`" style="max-width:100%;max-height:480px"></img>
              <br>
              Source: <a target="_blank" :href="$page.entry.source">{{$page.entry.source}}</a>
            </div>
          </b-col>
          <b-col md="4" lg="4" class="pt-3 pb-3" >
            <div style="position:absolute;top:30%">
            <p class="display-4 mb-0">{{$page.entry.title}}</p>
            <p class="lead">{{$page.entry.author}}</p>
              <p>
                <b-button v-if="!showOriginal" @click="showOriginal = !showOriginal">Show Original</b-button>
                <b-button v-else @click="showOriginal = !showOriginal">Show DeepArt</b-button>
              </p>
            </div>
          </b-col>


        </b-row>
      </b-container>
    </section>

    <b-container class="mt-5 mb-5">
      <b-row>
        <b-col order="2" order-lg="1" cols="12" lg="8" class="article-content">
          <div v-html="$page.entry.content" />
        </b-col>
        <b-col lg="3" order="1" order-lg="2" offset-lg="1" class>
          <SectionSidebar :record="$page.entry"></SectionSidebar>
        </b-col>
      </b-row>
    </b-container>


    <b-container fluid v-if="relatedRecords.length==2">

      <b-row class="text-center pt-5 bg-gray-100">
        <b-col>
          <h2 class="display-4">You might also like</h2>
        </b-col>
      </b-row>

      <b-row class="height-30 bg-gray-100 pb-5 related-records">

        <b-col sm="12" md="6" class="pr-5 pl-5 mt-5 border-right" v-for="relatedRecord in relatedRecords" :key="relatedRecord.node.id">
          <h4 class="">{{ relatedRecord.node.title }}</h4>
          <p v-html="relatedRecord.node.excerpt"></p>

          <g-link :to="recordLink(relatedRecord.node)" class="btn btn-lg btn-primary">Continue reading</g-link>

        </b-col>

      </b-row>
    </b-container>

  </DefaultLayout>
</template>

<page-query>
  query Article($recordId: ID!, $tags: [String]) {
    entry : article(id: $recordId) {
      title
      author
      image
      source
      content
      excerpt
      createdAt(format:"Do MMMM YYYY")
      timeToRead
      tags {
          title
          path
      },
      headings {
        depth
        value
        anchor
      },
    }

    related: allArticle(
      filter: { id: { ne: $recordId }, tags: {containsAny: $tags} }
    ) {
      edges {
        node {
          id
          title
          excerpt
          slug
        }
      }
    }


  }
</page-query>

<script>
import SectionHeader from "~/layouts/sections/article/HeaderBanner.vue";
import SectionSidebar from "~/layouts/sections/article/Sidebar.vue";
import { sampleSize } from "lodash";
export default {
  data() {
    return {
      showOriginal: false
    };
  },
  components: {
    SectionHeader,
    SectionSidebar
  },

  methods: {
    recordLink(record) {
      return `/articles/${record.slug}`;
    }
  },

  computed: {
    relatedRecords() {
      return sampleSize(this.$page.related.edges, 2);
    },
    setImage: function(){
      return require(`~/resources/images/art/${this.$page.entry.image}/deepart.jpg`);
    },
    setImage2: function(){
      return require(`~/resources/images/art/${this.$page.entry.image}/original.jpg`);
    }
  },

  metaInfo() {
    return {
      title: this.$page.entry.title
    };
  }
};
</script>

<style>
@import "https://github.githubassets.com/assets/gist-embed-d89dc96f3ab6372bb73ee45cafdd0711.css";
</style>

<style lang="scss">
  .article-content{
    p {
      color: #a09e9c;
      font-size: 95%;
    }
  }
</style>
