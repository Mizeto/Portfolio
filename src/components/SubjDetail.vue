<template>
    <div class="card my-2">
        <div class="card-body bg-info bg-opacity-10">
            <h4 class="card-title"> {{ subjs.term }}</h4>
            <h5 class="card-sub-title">รหัสวิชา {{ subjs.id }}</h5>
            <div class="card-sub-title">ชื่อวิชา {{ subjs.name }}</div>
            <div class="cart-text">ภาคการเรียน {{ subjs.semester }} ชั้นปีที่ {{ subjs.yr }}</div>
            <div class="cart-text">เกรด {{ subjs.Grade }}</div>
            <div class="cart-text">หน่วยกิต {{ subjs.credit }}</div>
        </div>
    </div>
    <button class="btn btn-sm btn-primary mx-2" 
        @click="editDetail(subjId)">แก้ไขข้อมูล
    </button>
    <button class="btn btn-sm btn-danger mx-2" 
        @click="delDetail(subjId)">ลบข้อมูล
    </button>
    <div class="row">
    <div class="col-lg-4 col-md-4 col-sm-6 mt-2">
        <label for="subjTerm" class="form-label">เทอม</label>
        <select id="subjTerm" class="form-select" v-model="subjs.term">
            <option value="Mid-Term">Mid-Term</option>
            <option value="Final-Term">Final-Term</option>
        </select>
    </div>
    <div class="col-lg-4 col-md-4 col-sm-6 mt-2">
        <label for="subjId" class="form-label">รหัสวิชา</label>
        <input type="text" id="subjId" class="form-control" v-model.trim="subjs.id" required />
    </div>
    <div class="col-lg-8 col-md-8 col-sm-6 mt-2">
        <label for="subjName" class="form-label">ชื่อรายวิชา</label>
        <input type="text" id="subjName" class="form-control" v-model.trim="subjs.name" required />
    </div>
    <div class="col-lg-3 col-md-4 col-sm-6 mt-2">
        <label for="" class="form-label">ภาคการเรียน</label>
        <div class="form-check">
            <input class="form-check-input" type="radio" id="subjsemester" value="Normal" v-model="subjs.semester" />
            <label class="form-check-label" for="subjsemester">Normal</label>
        </div>
        <div class="form-check">
            <input class="form-check-input" type="radio" id="subjsemester" value="Special" v-model="subjs.semester" />
            <label class="form-check-label" for="subjsemester">Special</label>
        </div>
    </div>
    <div class="col-lg-2 col-md-2 col-sm-3 mt-2">
        <label for="subjYr" class="form-label">ชั้นปี</label>
        <select id="subjYr" class="form-select" v-model="subjs.yr">
            <option value="1">ปี1</option>
            <option value="2">ปี2</option>
            <option value="3">ปี3</option>
            <option value="4">ปี4</option>
        </select>
    </div>
    <div class="col-lg-2 col-md-2 col-sm-3 mt-2">
        <label for="subjCredit" class="form-label">หน่วยกิต</label>
        <select id="subjCredit" class="form-select" v-model="subjs.credit">
            <option value="1">1</option>
            <option value="2">2</option>
            <option value="3">3</option>
        </select>
    </div>
    <div class="col-2 mt-4 d-flex align-items-center">
        <button id="btnSubmit" type="submit" class="btn btn-primary ">บันทึก</button>
    </div>
</div>
</template>

<script>
export default {
    emits: ['edit', 'delete'],
    name: 'SubjDetail',
    props: ['subjId'],
    data(){
        return {
            subjs:[]
        }
    },
    mounted(){
        fetch('http://localhost:3000/Subject/'+this.subjId)
        .then(res => res.json())
        .then(data => this.subjs=data)
        .catch(err => console.log(err.message))
    },
    methods:{
        handleEdit() {
            this.$emit('edit'); // Emit the 'edit' event
        },
        handleDelete() {
         this.$emit('delete'); // Emit the 'delete' event
        },
        editDetail(theId){
            this.$emit('edit',theId)
        },
        delDetail(theId){
            fetch('http://localhost:3000/Subject/'+theId,{
            method:'DELETE'
        })
            .then(this.$emit('delete'))
            .catch()
        }
    }
}
</script>

<style>

</style>