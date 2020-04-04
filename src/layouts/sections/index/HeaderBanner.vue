<template>
  <section class="height-50" style="background-color:#F8F9FD">
    <b-container>
      <b-row class="justify-content-center text-center">
        <b-col md="8" lg="6" class="pt-3 pb-3" style="margin-top:100px">
          <p class="display-4 mb-0">Deep Dream Abstract Art.</p>
          <p class="lead">Dreaming about abstract art</p>
        </b-col>
        <b-col md="4" lg="6" class="pt-3 pb-3">
          <ClientOnly>
          <b-carousel
                  id="carousel-fade"
                  style="text-shadow: 0px 0px 2px #000"
                  fade
                  indicators
                  img-height="480"
          >
            <b-carousel-slide
                    img-src="/images/art/1.png"
                    img-height="480"
            ></b-carousel-slide>
            <b-carousel-slide
                    img-src="/images/art/2.png"
                    img-height="480"
            ></b-carousel-slide>
            <b-carousel-slide
                    img-src="/images/art/3.png"
                    img-height="480"
            ></b-carousel-slide>
          </b-carousel>
          </ClientOnly>
        </b-col>

      </b-row>
    </b-container>
  </section>
</template>

