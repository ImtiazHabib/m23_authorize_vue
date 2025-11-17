<script setup>
import {computed, ref} from 'vue';
import { data } from './data';

const user_role = ref();

const select_role = computed( ()=>{
  if(user_role.value == 1) return 1;
  if(user_role.value == 2) return 2;

}

)
</script>

<template>
  <h1>Please select that you are admin or normal user </h1>

  <select  v-model="user_role"  class="form-select" aria-label="Default select example">
    <option value="1">Admin</option>
    <option value="2">Normal user</option>
  </select>



 <template v-if="select_role == 1">
    <div   class="card" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">{{ data.name }}</h5>
    <p class="card-text">{{ data.description }}</p>
  </div>
   </div>
 </template>

 <template v-if="select_role == 2">
    <p>
      As You are normal user you have not data 
    </p>
 </template>
 
</template>

<style scoped></style>
