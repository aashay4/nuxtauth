<template>
  <div>
    <div class="w3-main w3-content w3-padding" style="max-width:1200px;margin-top:100px">

  <!-- First Photo Grid-->
  <div class="w3-row-padding w3-padding-16 w3-center" id="food">
    <div class="w3-quarter">
      <p>Search Your Laptop </p>
      <Dropdown
        :articles="articles"
        v-on:selected="validateSelection"
        v-on:filter="getDropdownValues"
        :disabled="false"
        placeholder="Please select an animal">
      </Dropdown>
      <img v-if="selected.title != null" :src="require('~/assets/' + selected.imgpath)" style="width:100%">
      <h3>Selected animal: {{ selected.title || 'none' }}</h3>
      <h3>Selected COntent: {{ selected.body || 'none' }}</h3>
      <h3>Selected author: {{ selected.author || 'none' }}</h3>
      <h3>Selected imagepath: {{ selected.imgpath || 'none' }}</h3>
      <p>Just some random text, lorem ipsum text praesent tincidunt ipsum lipsum.</p>
    </div>
    <div class="w3-quarter">
      <p>Search Your Laptop </p>
      <Dropdown1
        :articles="articles"
        v-on:selected="validateSelection1"
        v-on:filter="getDropdownValues1"
        :disabled="false"
        placeholder="Please select an laptop">
      </Dropdown1>
      <img v-if="selected1.title != null" :src="require('~/assets/' + selected1.imgpath)" style="width:100%">
      <h3>Selected animal: {{ selected1.title || 'none' }}</h3>
      <h3>Selected COntent: {{ selected1.body || 'none' }}</h3>
      <h3>Selected author: {{ selected1.author || 'none' }}</h3>
      <h3>Selected imagepath: {{ selected1.imgpath || 'none' }}</h3>
      <p>Just some random text, lorem ipsum text praesent tincidunt ipsum lipsum.</p>
    </div>
    <div class="w3-quarter">
      <p>Search Your Laptop </p>
      <Dropdown
        :articles="articles"
        v-on:selected="validateSelection2"
        v-on:filter="getDropdownValues2"
        :disabled="false"
        placeholder="Please select an animal">
      </Dropdown>
      <img v-if="selected2.title != null" :src="require('~/assets/' + selected2.imgpath)" style="width:100%">
      <h3>Selected animal: {{ selected2.title || 'none' }}</h3>
      <h3>Selected COntent: {{ selected2.body || 'none' }}</h3>
      <h3>Selected author: {{ selected2.author || 'none' }}</h3>
      <h3>Selected imagepath: {{ selected2.imgpath || 'none' }}</h3>
      <p>Just some random text, lorem ipsum text praesent tincidunt ipsum lipsum.</p>
    </div>
    <div class="w3-quarter">
      <p>Search Your Laptop </p>
      <Dropdown
        :articles="articles"
        v-on:selected="validateSelection3"
        v-on:filter="getDropdownValues"
        :disabled="false"
        placeholder="Please select an animal">
      </Dropdown>
      <img v-if="selected3.title != null" :src="require('~/assets/' + selected3.imgpath)" style="width:100%">
      <h3>Selected animal: {{ selected3.title || 'none' }}</h3>
      <h3>Selected COntent: {{ selected3.body || 'none' }}</h3>
      <h3>Selected author: {{ selected3.author || 'none' }}</h3>
      <h3>Selected imagepath: {{ selected3.imgpath || 'none' }}</h3>
      <p>Just some random text, lorem ipsum text praesent tincidunt ipsum lipsum.</p>
    </div>
  </div>
</div>
  </div>
</template>
<script>
import Dropdown from '~/components/Dropdown.vue'
import Dropdown1 from '~/components/Dropdown1.vue'
  export default {
    components: { Dropdown, Dropdown1 },
    middleware: 'auth',
    async asyncData(context){
      const {data} = await context.$axios.get('/api/articles/')
      return {
        articles : data,
      }
    },
    name: 'filterpost',
    data () {
      return {
        articles: [],
        selected: { title: null, content: null, author: null },
        selected1: { title: null, content: null, author: null },
        selected2: { title: null, content: null, author: null },
        selected3: { title: null, content: null, author: null },
      }
    },
    methods: {
      validateSelection(selection) {
        this.selected = selection;
      },
      validateSelection1(selection1) {
        this.selected1 = selection1;
      },
      validateSelection2(selection2) {
        this.selected2 = selection2;
      },
      validateSelection3(selection3) {
        this.selected3 = selection3;
      },
      getDropdownValues(keyword) {
        console.log('You could refresh options by querying the API with '+keyword);
      },
      getDropdownValues1(keyword) {
        console.log('You could refresh options by querying the API with '+keyword);
      },
      getDropdownValues2(keyword) {
        console.log('You could refresh options by querying the API with '+keyword);
      }
    }
  }
</script>


<style type="text/css" scoped>
  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 3em;
  }
  h1 {
    font-weight: 100;
    font-size: 1.5em;
  }
  p {
    font-size: .8em;
    color: #ccc;
  }
</style>
