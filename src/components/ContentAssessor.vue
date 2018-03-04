<template>
  <div class="vue-yoast-bootstrap">
    <slot :results="assessorResults">
      <div class="list-group">
        <template 
          v-for="rating in ['feedback', 'bad', 'ok', 'good']" 
          v-if="typeof assessorResultsByRating[rating] !== 'undefined'">
          <div v-for="item in assessorResultsByRating[rating]" v-if="item.text != ''" class="list-group-item" >
            <span :class="['badge', 'badge-pill', 'mr-2']">&nbsp;</span>
            <span v-html="item.text"></span>
          </div>
        </template>
      </div>
    </slot>
  </div>
</template>

<script>
  import VueYoast from 'vue-yoast'
  export default {
    extends: VueYoast.ContentAssessor,
    methods: {
    },
    mounted () {
      console.log(VueYoast.ContentAssessor)
    }
  }
</script>