<template>
  <DefaultLayout>
    <SectionHeaderBanner :totalCount="$page.records.belongsTo.totalCount" :tag="$page.records.id"></SectionHeaderBanner>
    <section class="pt-5 mb-5">
      <b-container class="pb-5">
        <div>
          <b-row>
            <RecordCard
              v-for="edge in $page.records.belongsTo.edges"
              :key="edge.node.id"
              :record="edge.node"
            />
          </b-row>
        </div>
      </b-container>

      <Pagination
        :baseUrl="baseUrl"
        :currentPage="$page.records.belongsTo.pageInfo.currentPage"
        :totalPages="$page.records.belongsTo.pageInfo.totalPages"
        :maxVisibleButtons="5"
        v-if="$page.records.belongsTo.pageInfo.totalPages > 1"
      />
    </section>


  </DefaultLayout>
</template>


<script>
import RecordCard from "~/components/RecordCard.vue";
import Pagination from "~/components/Pagination.vue";
import SectionHeaderBanner from "~/layouts/sections/tag/HeaderBanner.vue";

export default {
  components: {
    RecordCard,
    Pagination,
    SectionHeaderBanner
  },
  computed: {
    baseUrl() {
      return `/tag/${this.$page.records.id}`
    }
  },
  metaInfo() {
    return {
      title: `Tag results for: ${this.$page.records.id}`,
      link: [
        { rel: 'stylesheet', href: '/css/customtags.css' },
      ]
    }
  },
  mounted() {
    console.log(`tag page: ${this.$page.records.id}`);
    // if (this.$page.records.id === 'DeepStyle') {
    //   console.log(`tag page: ${this.$page.otherval.id}`);
    // }

  }
};
</script>


<page-query>
query ($id: ID!, $page:Int) {
  records : tag(id: $id) {
    id
    title
    belongsTo(perPage: 9, page: $page) @paginate {
      totalCount
      pageInfo {
        totalPages
        currentPage
      }
      edges {
        node {
          __typename
          ... on Article {
            id,
            title,
            path,
            image,
            author,
            slug,
            excerpt,
            createdAt(format:"Do MMMM YYYY"),
            timeToRead,
            tags {
              title,
              path
            }
          }
        }
      }
    }
  }
}
</page-query>

