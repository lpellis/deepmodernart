<template>
  <div style="background-color:#F8F9FD">

    <div>
      <b-navbar toggleable="sm" type="light" variant="none">
        <b-navbar-brand href="#"><div >Deep Dream Abstract Art</div></b-navbar-brand>
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">

          <b-nav-item href="#" >Link</b-nav-item>
          <b-nav-item href="#" disabled>Disabled</b-nav-item>
          <b-nav-item href="#" disabled>Disabled</b-nav-item>
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
