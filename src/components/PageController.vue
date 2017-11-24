<template>
  <nav class="controller">
    <ul>
        <li v-for="index in pageNum" @click="changePage(index)" 
        :class="{current: index === currentPage}" 
        :data-index="index" class="controller-item"></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'page-controller',
  props: {
    pageNum: Number,
    currentPage: Number
  },
  methods: {
    changePage (index) {
      this.$emit('changePage', index);
    }
  },
  computed: {
    nextIndex () {
      if (this.currentPage === this.pageNum) {
        return this.pageNum
      } else {
        return this.currentPage + 1;
      }
    },
    prevIndex () {
      if (this.currentPage === 1) {
        return 1
      } else {
        return this.currentPage - 1;
      }
    }
  },
  mounted () {
    let _this = this;
    let timer = null;
    let start = 0;

    // 滚轮处理
    function scrollHandler (direction) {
      // 防止重复触发滚动事件
      if (timer != null) {
        return;
      }
      if (direction === 'down') {
        _this.changePage(_this.nextIndex);
      } else {
        _this.changePage(_this.prevIndex);
      }
      timer = setTimeout(function() {
        clearTimeout(timer);
        timer = null;
      }, 300);
    }

   
    if (Object.hasOwnProperty.call(window,'onmousewheel')) {
      // 监听滚轮事件
      window.addEventListener('mousewheel',function (event) {   // IE/Opera/Chrome
        let direction = event.wheelDelta > 0 ? 'up':'down';
        scrollHandler(direction);
      },false);
    } 
    // else {
      // window.addEventListener('DOMMouseScroll',function (event) {   // Firefox
        // let direction = event.detail > 0 ? 'up':'down';
        // scrollHandler(direction);
      // },false);
    // }

    // // 移动端触摸事件处理
    // window.addEventListener('touchstart', function (event) {
    //   start = event.touches[0].clientY;
    // })
    // window.addEventListener('touchmove', function (event) {
    //   event.preventDefault();
    // })
    // window.addEventListener('touchend', function (event) {
    //   let spacing = event.changedTouches[0].clientY - start;
    //   let direction;      
    //   if (spacing > 50) {
    //     direction = 'up';
    //     scrollHandler(direction);
    //   } else if (spacing < -50) {
    //     direction = 'down';
    //     scrollHandler(direction);
    //   }
    // })
  }
}
</script>

<style scoped>
  .controller {
    position: fixed;
    right: 20px;
    top: 50%;
    z-index: 99;
  }
  .controller ul {
    transform: translate3d(0,-50%,0);
    list-style: none;
    margin: 0;
    padding: 0;
  }
  .controller-item {
    cursor: pointer;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    margin-top: 10px;
    background-color: rgba(255, 255, 255, 0.3);
    transition: background-color 0.3s ease 0s;
  }
  .controller-item:hover {
    background-color: rgba(255, 255, 255, 0.7);
  }
  .controller-item.current {
    background-color: rgba(255, 255, 255, 1);
  }
</style>