<template>
    <section class="container pt-5" style="font-family: 'Andalé Mono', monospace;">
    <div class="Container">
        <div class="display-2" style="font-weight: bold;">Skill</div>
        <br><br>
        <div class="row row-cols-1 row-cols-md-3 g-5">
            <div class="col d-flex justify-content-center">
                <div class="card text-center" style="width: 20rem;">
                <img :src="python" class="card-img-top" alt="...">
                <div class="card-body">
                    <h5 class="card-title">{{ skill[0] }}</h5>
                </div>
                </div>
            </div>

            <div class="col d-flex justify-content-center">
                <div class="card text-center" style="width: 20rem;">
                <img :src="cpp" class="card-img-top" alt="...">
                <div class="card-body">
                    <h5 class="card-title">{{ skill[1] }}</h5>
                </div>
                </div>
            </div>

            <div class="col d-flex justify-content-center">
                <div class="card text-center" style="width: 20rem;">
                <img :src="java" class="card-img-top" alt="...">
                <div class="card-body">
                    <h5 class="card-title">{{ skill[2] }}</h5>
                </div>
                </div>
            </div>

            <div class="col d-flex justify-content-center">
                <div class="card text-center" style="width: 20rem;">
                <img :src="js" class="card-img-top" alt="...">
                <div class="card-body">
                    <h5 class="card-title">{{ skill[3] }}</h5>
                </div>
                </div>
            </div>

            <div class="col d-flex justify-content-center">
                <div class="card text-center" style="width: 20rem;">
                <img :src="html" class="card-img-top" alt="...">
                <div class="card-body">
                    <h5 class="card-title">{{ skill[4] }}</h5>
                </div>
                </div>
            </div>
            
            <div class="col d-flex justify-content-center">
                <div class="card text-center" style="width: 20rem;">
                <img :src="css" class="card-img-top" alt="...">
                <div class="card-body">
                    <h5 class="card-title">{{ skill[5] }}</h5>
                </div>
                </div>
            </div>
        </div>
        <br><br><br>
    </div>
  </section>
</template>

<script>
export default {
  name: "TheSkills",
  data() {
    return {
        skill: ['Python', 'C++', 'Java', 'JavaScript', 'HTML', 'CSS'],
        python: require('@/assets/icon/python.jpg'),
        cpp: require('@/assets/icon/c++.jpg'),
        java: require('@/assets/icon/java.jpg'),
        js: require('@/assets/icon/js.png'),
        html: require('@/assets/icon/html.jpg'),
        css: require('@/assets/icon/css.png')
    }
  }
};
</script>

<style>
</style>
