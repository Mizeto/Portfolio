<template>
    <section class="container pt-5" style="font-family: 'Andalé Mono', monospace;">
      <div class="Container">
            <div class="display-2" style="font-weight: bold;">About Me</div>
            <br>
            <span>
                <h3><b>Name:</b> <span style="font-weight: normal;">{{ name }}</span></h3>
                <h3><b>Nickname:</b> <span style="font-weight: normal;">{{ nickName }}</span></h3>
                <h3><b>Gender:</b> <span style="font-weight: normal;">{{ gender }}</span></h3>
                <h3><b>Age:</b> <span style="font-weight: normal;">{{ age }}</span></h3>
                <h3><b>Birthdate:</b> <span style="font-weight: normal;">{{ birthDate }}</span></h3>
                <h3><b>Hobbies:</b> <span style="font-weight: normal;">{{ hobbies[0] }}, {{ hobbies[1] }}, {{ hobbies[2] }}</span></h3>
                <h3><b>Telephone:</b> <span style="font-weight: normal;">{{ tel }}</span></h3>
                <h3><b>Email:</b> <span style="font-weight: normal;">{{ email }}</span></h3>
            </span>
            <br><br>
      </div>
    </section>
</template>

<script>
export default {
    name: 'AboutMe',
    data() {
        return {
            name: 'Mr.Nattawut Supapat',
            nickName: 'Poke',
            gender: 'Male',
            age: 21,
            birthDate: '9 January 2003',
            hobbies: ['Play Basket Ball', 'Play Vidio Game', 'Play Chess'],
            tel: '063-082-1353',
            email: 'natttawut.s@ku.th'
        }
    }
}
</script>

<style>

</style>
