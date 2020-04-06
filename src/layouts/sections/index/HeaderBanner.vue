<template>
  <section style="background-color:#fbe8da">
    <b-container>
      <b-row class="justify-content-center text-center">
        <b-col md="8" lg="6" class="pt-3 pb-3" style="margin-top:60px">
          <p class="display-4 mb-0">Deep Dream Abstract Art.</p>
          <p class="lead" style="color:gray">An AI dreams about Abstract Art</p>
          <g-link class="card-link" to="/articles"><h5>Explore</h5></g-link>
        </b-col>
        <b-col md="4" lg="6" class="pt-3 pb-3" >

          <b-carousel
                  id="carousel-fade"
                  style="text-shadow: 0px 0px 2px #000;width:380px;max-width:100%"
                  fade
                  indicators
          >
            <b-carousel-slide
                    img-src="/images/art/1.png"
            ></b-carousel-slide>
            <b-carousel-slide
                    img-src="/images/art/2.png"
            ></b-carousel-slide>
            <b-carousel-slide
                    img-src="/images/art/3.png"
            ></b-carousel-slide>
          </b-carousel>

        </b-col>

      </b-row>
    </b-container>
  </section>
</template>

