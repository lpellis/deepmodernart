<template>
  <DefaultLayout>
    <section style="background-color:#F8F9FD;">
      <b-container>
        <b-row class="justify-content-center text-center">
          <b-col md="8" lg="8" class="pt-3 pb-3">
            <div>

              <div class="d-md-none">
                <p class="display-4 mb-0">{{$page.entry.title}}</p>
                <p class="lead">{{$page.entry.author}}</p>
                <p>
                  <b-button v-if="!showOriginal" @click="showOriginal = !showOriginal">Show Original</b-button>
                  <b-button v-else @click="showOriginal = !showOriginal">Show DeepArt</b-button>
                </p>
              </div>

            </div>
            <img v-if="!showOriginal" :src="`/images/art/${$page.entry.image}/deepart.jpg`" style="max-width:100%;max-height:480px">
            <div v-if="showOriginal" style="font-size:80%">
            <img  :src="`/images/art/${$page.entry.image}/original.jpg`" style="max-width:100%;max-height:480px"></img>
              <br>
              Source: <a target="_blank" :href="$page.entry.source">{{$page.entry.source}}</a>
            </div>
          </b-col>
          <b-col md="4" lg="4" class="pt-3 pb-3 d-none d-md-block" >
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
          <h4>More Works</h4>
        </b-col>
      </b-row>

      <b-row align-h="around">

        <b-col colls="4" lg="4" md="4"  v-for="relatedRecord in relatedRecords" :key="relatedRecord.node.id">
          <p></p>
          <b-card class="h-60 infobox" footer-class="border-0">

            <b-card-title tag="h4">
              {{ relatedRecord.node.title }}
            </b-card-title>


            <b-card-text>
              <g-link class="card-link" :to="recordLink(relatedRecord.node)"><img  :src="`/images/art/${relatedRecord.node.image}/deepart.jpg`" style="max-width:100%;max-height:240px"></g-link>
              <br>
              {{ relatedRecord.node.author }}
            </b-card-text>

          </b-card>

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
          image
          author
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
  .infobox{
    border:1px solid #eff0f3;
    border-radius:2px;
    background-color:#F8F9FC;
    text-align:center;
  }
</style>
