<template>
  <section class="container pt-3" style="font-family: 'Andalé Mono', monospace;">
      <ul class="list-group">
        <li v-for="(sbj, id) in Subject_Grade" :key="id" class="list-group-item">
          <a style="font-weight: bold;" @click="setShow(sbj)">- {{ sbj.id }} {{ sbj.name }}</a>
          <div v-if="sbj.isShow">
                <SubjectDetail :sbjID="sbj.id" @delete="reload"/>
          </div>
        </li>
        <div v-if="isEdit">{{ editID }}</div>
      </ul>
  </section>
</template>

<script>
import SubjectDetail from "./SubjDetail.vue";
export default {
  name: "TheRecord",
  components: {
    SubjectDetail
  },
  data() {
    return {
      Subject_Grade: [],
      editID:"",
      isEdit:false
    };
  },
  mounted() {
    fetch('http://localhost:3000/Subject_Grade')
      .then(res => res.json())
      .then(data => (this.Subject_Grade = data))
      .catch(err => console.log(err.message));
  },
  methods: {
    setShow(theId) {
      theId.isShow = !theId.isShow;
    },
    reload() {
      this.$parent.showSubjList=!this.$parent.showSubjList
    }
  }
};
</script>

<style>
</style>