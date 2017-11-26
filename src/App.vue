<template>
  <div class="main">
    <div class="slide">
      <div class="block-warp">
        <div class="block">
          <div class="logo"></div>
          <div class="name">
            <h2>万成龙，男</h2>
            <div class="occupation">前端工程师</div>
          </div>
        </div>
        <div class="block">
          <div class="title">
            <img src="./assets/icon-user.svg" alt="">
            <span>简介</span>
          </div>
          <p class="profile">发的是佛少发达 富豪风混搭送饭活动啊非稻盛和夫冬奥发达奋斗啊😓奋斗啊话费活动啊奋斗啊哈佛的号发的好佛大和奋斗啊😓奋斗啊稅</p>
        </div>
        <div class="block">
          <div class="title">
            <img src="./assets/icon-phone.svg" alt="">
            <span>15133012038</span>
          </div>
        </div>
        <div class="block">
          <div class="title">
            <img src="./assets/icon-email.svg" alt="">
            <span>iwancl_217@163.com</span>
          </div>
        </div>
        <div class="block">
          <div class="title">
            <img src="./assets/icon-zuobiao.svg" alt="">
            <span>中国 河北·邯郸</span>
          </div>
        </div>
      </div>
    </div>
    <div class="content">
      <section class="item">
        <h2 class="head-title">教育背景</h2>
        <div class="xueli-warp">
          <div class="xueli-item" v-for="item in xueli">
            <span>{{item.date}}</span>
            <span>{{item.xuexiao}}</span>
            <span>{{item.zhuanye}}{{item.xueli}}</span>
          </div>
        </div>
      </section>
			<section class="item">
        <h2 class="head-title">自我评价</h2>
        <div class="my-self">
          
        </div>
      </section>
      <section class="item">
        <h2 class="head-title">工作经历</h2>
        <div class="job-warp">
          <div class="job-item" v-for="item in gongzuojingli">
            <div class="date">{{item.date}}</div>
            <div class="text">
              <h2><i class="circle"></i><span>{{item.name}}</span></h2>
              <div class="text-content">{{item.content}}</div>
            </div>
          </div>
          <div class="job-item">
            <div class="date">加油！2017</div>
            <div class="text">
              <h2><i class="circle"></i><span>越努力，越幸福</span></h2>
            </div>
          </div>
        </div>
      </section>
			<section class="item">
        <h2 class="head-title">项目经验</h2>
        <div class="job-warp">
          <div class="job-item" v-for="item in gongzuojingli">
            <div class="date">{{item.date}}</div>
            <div class="text">
              <h2><i class="circle"></i><span>{{item.name}}</span></h2>
              <div class="text-content">{{item.content}}</div>
            </div>
          </div>
          <div class="job-item">
            <div class="date">加油！2017</div>
            <div class="text">
              <h2><i class="circle"></i><span>越努力，越幸福</span></h2>
            </div>
          </div>
        </div>
      </section>
      <section class="item">
        <h2 class="head-title">技能评价</h2>
        <div class="skill-warp">
          <div class="skill-item" v-for="item in jinengpingjia">
            <span>{{item.name}}</span>
            <div class="progress">
              <span class="fill" :style="{width: item.size, backgroundColor: item.bgColor}"></span>
            </div>
          </div>
				<div class="skill-info"></div>
        </div>
      </section>
    </div>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        xueli: [{
          date: '2011.09 - 2014.06',
          xuexiao: '西安电子科技大学',
          zhuanye: '计算机应用技术',
          xueli: '(专科)'
        }],
        gongzuojingli: [{
          date: '2016.08 - 2017.11',
          name: '深圳前海白羽毛互联网金融服务有限公司',
          content: '在公司主要负责使用html、css开发页面'
        },{
          date: '2016.08',
          name: '深圳前海白羽毛互联网金融服务有限公司',
          content: '在公司主要负责使用html、css开发页面'
        },{
          date: '2016.08',
          name: '深圳前海白羽毛互联网金融服务有限公司',
          content: '在公司主要负责使用html、css开发页面'
        }],
        jinengpingjia: [{
          name: 'JAVASCRIPT',
          bgColor: '#bc0c10',
          size: '60%'
        },{
          name: 'ECMASCRIPT 6',
          bgColor: '#c96a60',
          size: '80%'
        }]
      }
    }
  }
</script>
<style lang="stylus" scoped>
  .main {
    width 100%
    height 100vh
    display flex
    background rgba(227,227,227, 0.3)
    .slide {
      width 225px
      height 100vh
      position relative
      background: linear-gradient(to bottom, #757c82 -20%, #15212d);
      box-shadow: 5px 0 5px -5px black;
      .block-warp {
        position absolute
        top 50%
        transform translateY(-50%)
        .block {
          padding 0 20px
          margin-bottom 22px
          &:nth-child(1) {
            margin-bottom 30px
          }
          &:nth-child(2) {
            margin-bottom 42px
          }
          .title {
            margin-left 5px
            img, span {
              vertical-align middle
            }
            img {
              width 18px
              margin-right 3px
            }
            span {
              color #ffffff
              font-size 14px
              letter-spacing 1px
            }
          }
          .profile {
            font-size 13px
            margin-top 8px
            color #bbbbbb
            line-height 20px
          }
          .logo {
            width 80px
            height 80px
            margin 0 auto
            border-radius 50%
            background-color #e3e3e3
            cursor pointer
          }
          .name {
            text-align center
            letter-spacing 1px
            h2 {
              font-weight normal
              font-size 18px
              color #e3e3e3
              margin-top 18px
            }
            .occupation {
              color #cacaca
              font-size 15px
            }
          }
        }
      }
    }
    .content {
      width calc(100vw - 275px)
      height calc(100vh - 40px)
      overflow-y auto
      padding 20px 30px 20px 25px
      .item {
        margin-bottom 55px
      }
      .head-title {
        margin-bottom 10px
        font-size 18px
        color #404b53
        letter-spacing 1px
      }
      .job-warp {
        margin-left 20px
        .job-item {
          display flex
          .date {
            width 130px
            text-align right 
            margin-top 2px
            font-weight 600
            font-size 15px
            color #b31b0b
          }
          .text {
            margin-left 15px
            h2 {
              position relative
              font-weight normal
              font-size 15px
              .circle, span {
                vertical-align middle
              }
              .circle {
                width 12px
                height 12px
                display inline-block
                margin-right 15px
                border 2px solid #b31b0b
                border-radius 50%
              }
            }
            .text-content {
              min-height 100px
              padding 5px 0 10px 22px
              margin-left 7px
              border-left 2px solid #d6d4d4
              font-size 13px
            }
          }
        }
      }
      .skill-warp {
        margin-left 20px
				.skill-info {
					margin-top 20px
				}
        .skill-item {
          display flex
          align-items center
          margin-bottom 8px
          span {
            margin-right 20px
            width 110px
            font-weight 600
            font-size 14px
            color #b31b0b
          }
          .progress {
            width 60%
            height 10px
            border-radius 10px
            background-color rgba(212,212,212,0.5)
            position relative
            overflow hidden
            .fill {
              height 100%
              position absolute
              left 0
              border-radius 10px
            }
          }
        }
      }
      .xueli-warp, .my-self, .skill-info{
        padding 10px 0 10px 25px
        background-color rgba(197, 207, 215, 0.2)
        border-left 5px solid rgba(184, 20, 2, 0.8)
        font-size 13px
        .xueli-item span{
          margin-right 20px
        }
      }
    }
  }
</style>
<style>
	* {
		margin: 0;
		padding: 0;
	}
  html, body {
		height: 100%;
		width: 100%;
		font-family: 'Avenir', Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
	}	
</style>



