<template>
    <section class="container pt-5" style="font-family: 'Andalé Mono', monospace;">
        <br><br>
        <div class="row">
            <div class="container col-lg-6 mt-5">
                <h1 class="display-2" style="font-weight: bold;">{{ name }}</h1>
                <br>
                <h4 class="display-6">A bit about me</h4>
                <div class="lead">
                    {{ detail }}
                </div>
            </div>
            <div class="col-lg-6">
                <div class="text-end">
                    <img class="rounded-circle" :src="profile" alt="Image" height="500" />
                </div>
            </div>
        </div>
        <br><br><br>
    </section>
</template>

<script>
export default {
    name: 'pageWelcome',
    data() {
        return {
            name: 'Nattawut Supapat',
            detail: 'I am studying in Computer Science in Faculty of Sciences at Sriracha at Kasetsart University Sriracha Campus. I am interested in Web and Application Developer, Software Engineer, and the Machine Learning.',
            profile: require('@/assets/image/Me.jpg')
        }
    }
}
</script>

<style>

</style>
