<template>
    <section class="container pt-5" style="font-family: 'Andalé Mono', monospace;">
        <div class="container">
          <div class="display-2" style="font-weight: bold;">Hobbies</div>
          <div class="row justify-content-center py-5">
            <div class="col-lg-3 col-md-6 col-sm-12">
              <div class="card text-center">
                <img :src="game" class="card-img-top" />
                <div class="card-body">
                  <h5 class="card-title">{{ hobbie[0] }}</h5>
                </div>
              </div>
            </div>

            <div class="col-lg-3 col-md-6 col-sm-12">
              <div class="card text-center">
                <img :src="music" class="card-img-top" />
                <div class="card-body ">
                  <h5 class="card-title">{{ hobbie[1] }}</h5>
                </div>
              </div>
            </div>

            <div class="col-lg-3 col-md-6 col-sm-12">
              <div class="card text-center">
                <img :src="movie" class="card-img-top" />
                <div class="card-body">
                  <h5 class="card-title">{{ hobbie[2] }}</h5>
                </div>
              </div>
            </div>
          </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'TheHobbies',
    data() {
      return {
        hobbie: ['Play Basket Ball', 'Play Video Game', 'Play Chess'],
        game: require('@/assets/image/basketball.jpg'),
        music: require('@/assets/image/videogame.jpg'),
        movie: require('@/assets/image/chess.jpg')
      }
    }
}
</script>

<style>

</style>