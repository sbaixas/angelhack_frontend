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

   <img class="main-logo" src="static/logo.png">

    <div v-bind:class="amplifyUI.formField">
      <input type="text" class="input" autofocus v-model="search" placeholder="Search a paper" size="50">
    </div>
    <br>
    <button type="button" class="button" v-on:click="handleClick">Search</button>
    
  </div>
</template>

<script>
import * as AmplifyUI from '@aws-amplify/ui';
import { API } from 'aws-amplify'

export default {
  name: 'Home',
  data () {
    return {
      search:'',
      amplifyUI: AmplifyUI,
      options:{
        username:"bleh"
      }
    }
  },
  methods:{
    handleClick(event){
      this.getItems();
    },
    getItems: async () => {
      let myInit = {
          body: {}
      };
      console.log('Search text:', await API.get('documents', '/items', myInit));
    }
  }
}
</script>
<style type="text/css">
@import '../Theme.css';

.button {
  min-width: 30%;
  display: inline-block;
  margin-bottom: 0;
  font-size: 12px;
  font-weight: 400;
  line-height: 1.42857143;
  text-align: center;
  white-space: nowrap;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  user-select: none;
  background-image: none;
  color: var(--button-color);
  background-color: var(--button-background-color);
  border-color: #ccc;
  text-transform: uppercase;
  padding: 14px 0;
  letter-spacing: 1.1px;
  border: none;
}

.button:active {
  opacity: 1;
  background-color: var(--button-click);
}

.button:hover,
.signInButton:hover {
  opacity: 0.8;
}

.button:disabled {
  opacity: 1;
  cursor: auto;
  background-color: var(--ion-color-primary-tint);
}

.input {
  display: block;
  width: 100%;
  padding: 16px;
  font-size: 14px;
  color: var(--input-color);
  background-color: var(--input-background-color);
  background-image: none;
  border: 1px solid var(--lightGrey);
  border-radius: 3px;
  box-sizing: border-box;
  margin-bottom: 10px;
}

.input:disabled {
  color: #545454;
  background-color: var(--silver);
}

.inputLabel {
  color: var(--input-color);
  font-size: 14px;
  margin-bottom: 8px;
}

.label {
  color: var(--input-color);
}

.radio {
  margin-right: 18px;
  vertical-align: bottom;
}
</style>
