<template>
  <view class="content">
      <!--<Back></Back>-->
    <view class="toolsList">
      <view v-for="(item,index) in toolsList" :key="index" class="item animated fadeInUp" :class="item.delay">
        <image :src="item.bgc" mode="aspectFill"></image>
        <view class="bgc"></view>
        <view class="box">
          <text class="title">{{item.title}}</text>
          <text class="tips">{{item.tips}}</text>
          <navigator :url="item.src" class="link animated ">
            {{item.goTo}}
            <text class="iconfont iconicon-right"></text>
          </navigator>
        </view>
      </view>
    </view>
  </view>
</template>

<script>
    /*
   * https://ae01.alicdn.com/kf/Ua9f26b8d6723498bb252d01ee6d1a63da.jpg
   *https://ae01.alicdn.com/kf/U75ffe24ecbdd4269aef5e4dff1023899U.jpg
   *https://ae01.alicdn.com/kf/U9d979e95fb5a4dc2bd426f0cff272f0bO.jpg
   *https://ae01.alicdn.com/kf/U49c1ce435b9b4cc1a3cb4d1e5950b626T.jpg
   *https://ae01.alicdn.com/kf/Ufe15fd5d8dc5454f978547eb652ebc31y.jpg
   *https://ae01.alicdn.com/kf/Uf0b788f6ed1a4c65bafac6e86df00419N.jpg
   * https://ae01.alicdn.com/kf/U01fa7358b55f4830866f417e34b41b28l.jpg
   * https://ae01.alicdn.com/kf/U5b6b2023f2bc445c86409711bc6b56bca.jpg
   * https://ae01.alicdn.com/kf/U83db8e0e4d404533ba06d6bb24a2e4ebr.jpg
   * */
    // import Back from '../../components/Back'
    export default {
        components:{
            // Back
        },
        data() {
            return {
                delay:3,
                flag:true,
                toolsList: [{
                    title: '欢喜如你',
                    tips: '斯人如彩虹，遇上方知有',
                    bgc: 'https://hq-one-stand.oss-cn-shenzhen.aliyuncs.com/one-stand/photo/20200611/icon11.jpg',
                    src: 'enjoy?type=default',
                    goTo: '进入',
                    delay:''
                },
                    {
                        title: '猜你所享',
                        tips: '猜你所想，分享日常',
                        bgc: 'https://hq-one-stand.oss-cn-shenzhen.aliyuncs.com/one-stand/photo/20200611/icon6.jpg',
                        src: 'enjoy?type=friendly',
                        goTo: '进入',
                        delay:'delay-200ms'
                    },
                    {
                        title: '心灵鸡汤',
                        tips: '你在鸡汤里下毒。。',
                        bgc: 'https://hq-one-stand.oss-cn-shenzhen.aliyuncs.com/one-stand/photo/20200611/icon10.jpg',
                        src: 'enjoy?type=sad',
                        goTo: '进入',
                        delay:'delay-200ms'
                    },
                    {
                        title: '今夕何年',
                        tips: '故乡今夜思千里，霜鬓明朝又一年',
                        bgc: 'https://hq-one-stand.oss-cn-shenzhen.aliyuncs.com/one-stand/photo/20200611/icon9.jpg',
                        src: 'newYear',
                        goTo: '进入',
                        delay:'delay-400ms'
                    },
                    {
                        title: '心如止水',
                        tips: '让身心回归自然的拥抱',
                        bgc: 'https://hq-one-stand.oss-cn-shenzhen.aliyuncs.com/one-stand/photo/20200611/icon1.jpg',
                        src: 'photoShop',
                        goTo: '进入',
                        delay:'delay-600ms'
                    },
                    {
                        title: '初音未来',
                        tips: '动次打次~你能找到彩蛋嘛~',
                        bgc: 'https://hq-one-stand.oss-cn-shenzhen.aliyuncs.com/one-stand/photo/20200611/icon60.jpg',
                        src: 'game',
                        goTo: '进入',
                        delay:'delay-600ms'
                    },
                    {
                        title: '敬请期待',
                        tips: '不如给程序猿小哥哥资助点硬币',
                        bgc: 'https://hq-one-stand.oss-cn-shenzhen.aliyuncs.com/one-stand/photo/20200611/icon52.png',
                        src: 'more',
                        goTo: '可怜',
                        delay:'delay-600ms'
                    }
                ]
            }
        },
    }
</script>
<style>
  page{
    /*background: linear-gradient(to bottom, rgb(35, 37, 38), rgb(65, 67, 69));*/
  }
</style>
<style lang="less" scoped>
  .content {
    padding: 20px 0;
    background: linear-gradient(to bottom, rgb(35, 37, 38), rgb(65, 67, 69));

    .toolsList {
      .item {
        width: 94%;
        height: 200px;
        position: relative;
        left: 3%;
        border-radius: 15px;
        margin-bottom: 20px;

        &:last-of-type{
          margin-bottom: 0;
        }

        image {
          width: 100%;
          height: 100%;
          position: absolute;
          border-radius: 15px;
          top: 0;
          left: 0;
          z-index: 1;
        }

        .bgc{
          position: absolute;
          z-index: 2;
          width: 100%;
          height: 100%;
          opacity: 0.4;
           background-color: #000;
          border-radius: 15px;
        }
        .box{
          position: absolute;
          z-index: 3;
          width: 100%;
          height: 100%;

          text{
            color: #fff;
            display: block;
            margin-left: 8%;
            font-weight: lighter;
            margin-bottom: 10upx;
          }

          .title{
            font-size: 60upx;
            margin-top: 10%;
          }

          .tips{
            font-size: 26upx;
          }

          navigator {
            position: absolute;
            right: 8%;
            top: 50%;
            transform: translate(0,-50%);
            font-size: 38upx;
            color: #fff;
            z-index: 2;
            width: 175upx;
            height: 40px;
            line-height: 40px;
            padding-left: 15upx;
            text-align: center;
            border: 1upx solid #fff;
            border-radius: 60upx;

            text{
              display: inline-block;
              margin-left: 0;
              margin-bottom: 0;
            }
          }
        }
      }
    }
  }
</style>
