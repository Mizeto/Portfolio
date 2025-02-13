<template>
    <p class="h5 text-secondary" @click="clearShow">ผลการเรียน</p>
    <ul class="list-group">
        <li v-for = "(subj, id) in subjs" :key="id" class="list-group-item list-group-item-action">
            <a href="#a" @click="setShow(subj)">
                <div>{{ subj.id }}  name : {{ subj.name }} </div>
            </a>
            <div v-if="subj.isShow">
                <SubjDetail :subjId=subj.id @edit ="showEdit" @delete="reload"/>
            </div>
        </li>
        <div v-if="isEdit">
            {{ EditId }}
        </div>
    </ul>
</template>

<script>
import SubjDetail from './SubjDetail.vue';
export default {
    name: 'SubjList',
    components: {
        SubjDetail
    },
    data(){
        return {
            subjs:[],
            isEdit: false,
            EditId: ''
        }
    },
    mounted(){
        fetch('http://localhost:3000/Subject')
        .then(res => res.json())
        .then(data => this.subjs=data)
        .catch(err => console.log(err.message))
    },
    methods:{
        setShow(theId)
        {
            theId.isShow = !theId.isShow    
        },
        showEdit(subjId)
        {
            this.EditId = subjId
            this.isEdit = !this.isEdit
        },
        reload(){
            this.$parent.showSubjList = !this.$parent.showSubjList
        }
    }
}
</script>

<style></style>