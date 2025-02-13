<template>
    <div class="card">
        <div class="card-body">
            <h5 class="text-primary">แก้ไขข้อมูล</h5>
            <form @submit.prevent="handleSubmit"></form>
        </div>
    </div>
    <div class="alert alert-success mt-2" v-show="editSuccess">
        แก้ไขข้อมูล {{ subjs.id }} - {{ SubjList.name }} สำเร็จ
    </div>
    <div class="alert alert-danger mt-2" v-show="EditError">
        {{ errMessage }}
    </div>
</template>

<script>
export default {
    name: "SubjAdd",
    props: 'subjId',
    data(){
        return{
            subjs: [],
            editSuccess: false,
            editError : false,
            errMessager: ''
        }
    },
    mounted()
    {
    fetch('http://localhost:3000/Subject' + this.subjIdId)
        .then(res => res.json())
        .then(data => this.subjs = data)
        .catch(err => console.log(err.message))
    },
    methods:
    {
        handleSubmit()
        {
            let subjects = 
            {
                term:this.subjs.term,
                id:this.subjs.id,
                name:this.subjs.name,
                semester:this.subjs.semester,
                yr:this.subjs.yr,
                grade:this.subjs.grade,
                credit:this.subjs.credit,
            }
            fetch('http://localhost:3000/Subject' + this.subjId,
            {
                method: 'PATCH',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(subjects)
            })
                .then(() => {
                    this.editSuccess = false
                })
                .catch((err) => {
                    this.editError = false
                    this.editMessage = err
                })
        }

    }

}
</script>

<style>

</style>