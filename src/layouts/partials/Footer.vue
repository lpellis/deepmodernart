<template>
  <footer class="bg-gray-800">
    <b-container>
      <b-row align-h="between" align-v="center">
        <b-col cols="auto">
          <ul class="list-inline mb-0">
            <li class="list-inline-item mb-0">
            </li>
          </ul>
        </b-col>
        <b-col cols="auto" class="text-sm-right">
          <ul class="list-inline mb-0">
            <li class="list-inline-item mb-0">

                <g-link to="/credits" class="nav-link">
                  About
                </g-link>

            </li>
            <li class="list-inline-item mb-0">
              <b-navbar-brand class="mb-0">
              <a href="https://twitter.com/deepabstractart" target="_blank" class="nav-link text-light" alt="@deepabstractart" rel="noopener">
                <font-awesome :icon="['fab', 'twitter']"></font-awesome>
              </a>
              </b-navbar-brand>
            </li>
          </ul>
        </b-col>
      </b-row>
    </b-container>
  </footer>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>
