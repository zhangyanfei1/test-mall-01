<template>
  <div class="tab-control">
    <div @click="itemClick(index)" class="tab-controll-item" :class="{active: index === currentIndex}" v-for="(item, index) in titles" :key="index">
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
      currentIndex: 0,
       currentType: 'pop',
    }
  },
  methods: {
    itemClick (index) {
      this.currentIndex = index;
      this.$emit('tabClick', index)
    }
  }
}
</script>

<style scoped>
.tab-control {
  display: flex;
  line-height: 40px;
  height: 40px;
  font-size: 15px;
  text-align: center;
}

.tab-controll-item {
  flex: 1;
}

.active {
  color: var(--color-high-text);
}

.active span {
    border-bottom: 3px solid var(--color-tint);
  }
</style>