<template>

<v-footer height="auto">
    <v-card
      flat
      tile
      class="indigo lighten-1 white--text text-xs-center"
      style="background: #302B2B !important"
    >

      <div class="social">
        <Row>

          <Col :lg="6">
          <div class="simi">
          <Icon class="si" type="android-phone-portrait"></Icon> <a href="tel:+3544536707"> <span>+354</span> 4536707</a>
          </div><!-- .simi -->
          </Col>

          <Col :lg="6">
          <div class="face">
          <Icon class="fb" type="social-facebook"></Icon>
          </div><!-- .face -->
          </Col>

          <Col :lg="6">
          <div class="insta">
          <Icon class="ig" type="social-instagram"></Icon>
          </div><!-- .insta -->
          </Col>

          <Col :lg="6">
          <div class="email">
          <Icon class="em" type="email"></Icon>
          </div><!-- .email -->
          </Col>

          </Row>
      </div><!-- .social -->

        <div class="textlogo">
          <span class="copy"><img v-bind:src="logo" alt=""></span>
        </div>

    </v-card>
  </v-footer>

</template>


<script>
export default {
data () {

return {
     logo: "./static/logo.png",

    }
  }
}
</script>