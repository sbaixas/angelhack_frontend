/*
 * Copyright 2017-2017 Amazon.com, Inc. or its affiliates. All Rights Reserved.
 *
 * Licensed under the Apache License, Version 2.0 (the "License"). You may not use this file except in compliance with
 * the License. A copy of the License is located at
 *
 *     http://aws.amazon.com/apache2.0/
 *
 * or in the "license" file accompanying this file. This file is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR
 * CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions
 * and limitations under the License.
 */

<template>
  <div class="container shifted" style="text-align: center">
    <img src="static/logo.png">
    <div class="form-group">
      <br>
      <input type="text" class="form-control" name="searchBar" v-model="search" placeholder="Search a paper" size="50">
    </div>
    <br>
    <button type="button" class="btn btn-success"@click="handleClick">Search</button>
    
  </div>
</template>

<script>

export default {
  name: 'Home',
  data () {
    return {
      search:''
    }
  },
  methods:{
    handleClick(event){
      console.log('Search text:', this.search)
    }
  }
}
</script>
