<template>
  <div style="background-color:#F8F9FD">

    <div>
      <b-navbar toggleable="sm" type="light" variant="none">
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <b-navbar-brand href="/" style="color:gray">
          <img style="width:32px;border-radius:4px"  class="d-inline-block align-top" src="https://q4j2g5j9.stackpathcdn.com/ddg-thumbs/xs/2de0b0664bd7b6ef385cd579d75a9046fd522bfa.jpg" alt="Kitten">
          DeepAbstract Art
        </b-navbar-brand>
        <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">

          <b-nav-item href="#" >Latest Art</b-nav-item>
          <b-nav-item href="#" >Resources</b-nav-item>
          <b-nav-item href="#" >About</b-nav-item>
        </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>
<script>

export default {

  components: {
  },

  data() {
    return {
    };
  },

};
</script>
