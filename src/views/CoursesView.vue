
<template>
  <div class="container py-5">
    <div class="row">
      <div class="col-lg-3">
        <CourseFilter @category-updated="filterCourses"/>
      </div>
      <div class="col-lg-9">
        <CourseList :courses="filteredCourses" />
      </div>

    </div>
  </div>

</template>

<script>

  import CourseList from '@/components/CourseList.vue'
  import CourseFilter from '@/components/CourseFilter.vue'
  import {courses} from '../tem-data'
  export default {
    name: 'CoursesPage',
    components:{
      CourseList,
      CourseFilter
    },
    data(){
      return{
        courses: courses,
        filteredCourses: courses
      }
    },
      methods:{
        filterCourses(selectedCategory){
          this.filteredCourses = this.courses.filter(course =>selectedCategory.includes(course.category_id))
        }
      }
    }
  
</script>