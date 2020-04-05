<template>
  <div style="background-color:#515151">

    <div>
      <b-navbar toggleable="sm" type="dark" variant="none">
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <b-navbar-brand href="/" style="color:gray">
          <img style="width:32px;border-radius:4px"  class="d-inline-block align-top" src="https://q4j2g5j9.stackpathcdn.com/ddg-thumbs/xs/2de0b0664bd7b6ef385cd579d75a9046fd522bfa.jpg" alt="Kitten">

        </b-navbar-brand>
        <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">

          <b-nav-item-dropdown text="Explore Art" right>
            <b-dropdown-item to="/tag/deep-style">Deep Style Transfer</b-dropdown-item>
            <b-dropdown-item to="/tag/deep-dream">Deep Dream</b-dropdown-item>
          </b-nav-item-dropdown>
          <b-nav-item to="/resources" >Resources</b-nav-item>
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
