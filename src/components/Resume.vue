<template>
  <div id="app" class="app">
    <page :currentPage="currentPage">
      <h1 class="text-center">项目介绍</h1>
      <section class="animate">
        
      </section>
    </page>
    <page :currentPage="currentPage">
      <h1 class="text-center">配置说明</h1>
      <section class="animate move-left">
        
      </section>
    </page>
    <page :currentPage="currentPage">
      <h1 class="text-center">方法说明</h1>
      <section class="animate move-left">
        
      </section>
    </page>
    <page :currentPage="currentPage">
      <h1 class="text-center">作者信息</h1>
      <section class="animate move-left">
        
      </section>
    </page>
    <page-controller :pageNum="pageNum" :currentPage="currentPage" @changePage="changePage"></page-controller>
  </div>
</template>

<script>
import Page from './Page.vue';
import PageController from './PageController.vue';
export default {
  components: {
    Page, PageController
  },
  data() {
    return {
      currentPage: 1,
      options: [{
        background: 'rgba(229, 199, 46, 1)',
        color: '#fff',
        isCenter: true,
      }, {
        background: 'rgba(79, 204, 76, 1)',
        color: '#fff',
        isCenter: true,
      }, {
        background: 'rgba(233, 84, 84, 1)',
        color: '#fff',
        isCenter: true,
      }, {
        background: 'rgba(46, 153, 229, 1)',
        color: '#fff',
        isCenter: true,
      }]
    }
  },
  computed: {
    pageNum() {
      return this.options.length;
    }
  },
  methods: {
    changePage(index) {
      this.currentPage = index;
    }
  },
  mounted() {
    this.$children.forEach((child, index) => {
      // 动态设置各个page内的options
      if (child.option === null) {
        let childOption = this.options[index];
        this.$set(childOption, 'index', index + 1);
        child.option = childOption;
      }
    });
  }
}
</script>

<style>

.app {
  height: 100%;
  width: 100%;
}
/* 下面的是与fullPage无关的样式 */
.animate {
  transition: all 1s ease-out 0s;
}
.move-left {
  transform: translateX(-1000%);
}
.move-right {
  transform: translateX(1000%);
}
@media screen and (max-width:768px) {
  html,
  body {
    font-size: 12px;
  }
}
a {
  text-decoration: none;
  color: inherit;
}
a:hover {
  text-decoration: underline;
}
.person-img {
  width: 223px;
  height: 185px;
  float: left;
  background-color: #fff;
  box-shadow: 3px 3px 10px #999;
}
.person-img img {
  height: 100%;
  width: 100%;
}
.person-basic-info {
  overflow: hidden;
  float: right;
  margin-left: 40px;
}
.info-line {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: flex-start;
}
.text-center {
  text-align: center;
}
.text-bold {
  font-weight: bold;
}
.demo-intro {
  text-indent: 2em;
}
dt {
  font-weight: bold;
  font-size: 16px;
}
ul {
  padding-left: 1em;
}
.avatar {
  margin: 10px auto;
  display: block;
  box-shadow: 1px 1px 5px #666;
}
.author-info {
  text-align: center;
}
</style>