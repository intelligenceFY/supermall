<template>
  <div class="recommend">
    <div v-for="(item,key) in recommends"
         :key="key"
         class="recommend-item">
      <a :href="item.link">
        <img :src="item.image"
             alt="">
        <div>{{item.title}}</div>
      </a>
    </div>
  </div>
</template>

<script>


export default {
  name: 'RecommendView',
  props: {
    recommends: {
      type: Array,
      default () {
        return []
      }
    }
  }
}

</script>

<style>
.recommend {
  display: flex;
  flex-direction: row;
  width: 100%;
  justify-content: space-between;
  padding: 10px 0 20px;
  border-bottom: 10px solid #eee;
}
.recommend-item {
  text-align: center;
  flex: 1;
}
.recommend-item img {
  width: 70px;
  height: 70px;
  margin-bottom: 10px;
}
</style>
