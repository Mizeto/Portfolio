<template>
  <section class="container pt-5" style="font-family: 'Andalé Mono', monospace;">
        <div class="Container">
            <div class="display-2" style="font-weight: bold;">Education</div>
            <br>
            <div v-for="(edu, index) in education" :key="index" class="card mb-3" style="max-width: 1250px;">
                <div class="row g-0">
                    <div class="col-md-4">
                        <img :src="edu.image" class="img-fluid rounded-start" alt="...">
                    </div>
                    <div class="col-md-8">
                        <div class="card-body">
                            <h2 class="card-title" style="font-weight: bold;">{{ edu.times }}</h2>
                            <h4 class="card-text">{{ edu.detail }}</h4>
                            <h4 class="card-text">{{ edu.education }}</h4>
                        </div>
                    </div>
                </div>
            </div>
            <br><br>
        </div>
    </section>
</template>

<script>
export default {
    name: 'TheEducation',
    data() {
        return {
            education: [
                {
                    times: '2022 - Present',
                    detail: 'Computer Science, Faculty of Sciences at Sriracha',
                    education: 'Kasetsart University Sriracha Campus',
                    image: require('@/assets/image/sci.jpeg')
                },
                {
                    times: '2016 - 2021',
                    detail: 'High School certificate',
                    education: 'Hadammara Aksornlukwittaya School',
                    image: require('@/assets/image/had.jpg')
                }
            ]
        }
    }
}
</script>

<style>

</style>
