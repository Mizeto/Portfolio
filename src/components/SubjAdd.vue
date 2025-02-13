<template>
  <div class="card">
    <div class="card-body">
        <form @submit.prevent="handleSubmit()">
            <div class="row">
                <div class="col-lg-2 col-md-3 col-sm-4 mt-2">
                    <label for="subjTerm" class="form-label">เทอม</label>
                    <select id="subjTerm" class="form-select" v-model="subjs.term">
                        <option value="Mid-Term">Mid-Term</option>
                        <option value="Final-Term">Final-Term</option>
                    </select>
                </div>
                <div class="col-lg-4 col-md-4 col-sm-6 mt-2">
                    <label for="subjId" class="form-label">รหัสวิชา</label>
                    <input type="text" id="subjId" class="form-control" v-model.trim="subjs.id" />
                </div>
                <div class="col-lg-8 col-md-8 col-sm-6 mt-2">
                    <label for="subjName" class="form-label">ชื่อรายวิชา</label>
                    <input type="text" id="subjName" class="form-control" v-model.trim="subjs.name" />
                </div>
                <div class="col-lg-2 col-md-3 col-sm-4 mt-2">
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
                
                <div class="col-lg-2 col-md-3 col-sm-4 mt-2">
                    <label for="subjYr" class="form-label">ชั้นปี</label>
                    <select id="subjYr" class="form-select" v-model="subjs.yr">
                        <option value="1">ปี1</option>
                        <option value="2">ปี2</option>
                        <option value="3">ปี3</option>
                        <option value="4">ปี4</option>
                    </select>
                </div>
                <div class="col-lg-2 col-md-3 col-sm-4 mt-2">
                    <label for="subjGrade" class="form-label">เกรด</label>
                    <select id="subjGrade" class="form-select" v-model="subjs.grade">
                        <option value="A">A</option>
                        <option value="B+">B+</option>
                        <option value="B">B</option>
                        <option value="C+">C+</option>
                        <option value="C">C</option>
                        <option value="D+">D+</option>
                        <option value="D">D</option>
                        <option value="F">F</option>
                    </select>
                </div>
                <div class="col-lg-2 col-md-3 col-sm-4 mt-2">
                    <label for="subjcredit" class="form-label">หน่วยกิต</label>
                    <select id="subjcredit" class="form-select" v-model="subjs.credit">
                        <option value="1">1</option>
                        <option value="2">2</option>
                        <option value="3">3</option>
                    </select>
                </div>
                <div class="col-2 mt-4 d-flex align-items-center">
                    <button id="btnSubmit" type="submit" class="btn btn-primary">Save</button>
                </div>
            </div>
        </form>
    </div>
  </div>
  <div class="alert alert-success mt-2" v-show="addSuccess">
    บันทึกข้อมูล {{ subjs.id }} - {{ subjs.name }} สำเร็จ
  </div>
  <div class="alert alert-danger mt-2" v-show="addError">
    {{ errMessage }}
  </div>
</template>

<script>
export default {
    name: 'SubjAdd',
    data(){
        return{
            addSuccess: false,
            errMessage: '',
            addError: false,
            subjs: {
                grade: "",
                term: "",
                id: "",
                name: "",
                semester: "",
                yr: "",
                credit: "",
                isShow: false,
            },
        };
    },
    methods:{
        handleSubmit()
        {
            let subjs =
            {
                term:this.subjs.term,
                id:this.subjs.id,
                name:this.subjs.name,
                semester:this.subjs.semester,
                yr:this.subjs.yr,
                grade:this.subjs.grade,
                credit:this.subjs.credit,
                isShow:false
            }
            fetch('http://localhost:3000/Subject',{
            method:'POST',
            headers:{'Content-Type':'application/json'},
            body:JSON.stringify(subjs)
            })
            .then(()=>{
                this.addSuccess=true
            })
            .catch((err)=>{
            this.addError=true
            this.errMessage=err
            })
        }
    },
};
</script>

<style></style>