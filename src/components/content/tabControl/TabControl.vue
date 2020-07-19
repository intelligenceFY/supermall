<template>
  <div class="tab-control">
    <div v-for="(item,index) in titles"
         :key="(item,index)"
         :class="{active:index===currentIndex}"
         @click="itemClick(index)"
         class="tab-control-item">
      <span>{{item}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TabControl',
  props: {
    titles: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      currentIndex: 0
    }
  },
  methods: {
    itemClick (index) {
      this.currentIndex = index;
    }
  }
}
</script>

<style>
.tab-control {
  display: flex;
  width: 100%;
  font-size: 15px;
  height: 40px; /*可以继承 */
  line-height: 40px; /*可以继承 */
  background-color: #fff;
  z-index: 9;
}
.tab-control-item {
  text-align: center;
  flex: 1;
}
.tab-control-item span {
  padding: 5px;
}
.active {
  color: var(--color-high-text);
}
.active span {
  border-bottom: 3px solid var(--color-high-text);
}
</style>