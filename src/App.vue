<template>
  <div id="app">
    <div>
      <div class="list-box" @scroll="scrollFun">
        <ComList :pbList="pbList" ref="compList"></ComList>
      </div>
    </div>
  </div>
</template>

<script>
import ComList from './components/comList.vue'
export default {
  name: 'testList',
  components: {
    ComList
  },
  data () {
    return {
      // 瀑布流数据
      pbList: [
        {
          url: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg3.doubanio.com%2Fview%2Fphoto%2Fm%2Fpublic%2Fp2650049201.jpg&refer=http%3A%2F%2Fimg3.doubanio.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664935370&t=d4bf3e4d352c277a1bdebfcc8fda959f'
        },
        {
          url: 'https://img1.baidu.com/it/u=2911909188,130959360&fm=253&fmt=auto&app=138&f=JPEG?w=440&h=641'
        },
        {
          url: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg3.doubanio.com%2Fview%2Fphoto%2Fm%2Fpublic%2Fp2650049201.jpg&refer=http%3A%2F%2Fimg3.doubanio.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664935370&t=d4bf3e4d352c277a1bdebfcc8fda959f'
        },
        {
          url: 'https://img1.baidu.com/it/u=2911909188,130959360&fm=253&fmt=auto&app=138&f=JPEG?w=440&h=641'
        },
        {
          url: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg3.doubanio.com%2Fview%2Fphoto%2Fm%2Fpublic%2Fp2650049201.jpg&refer=http%3A%2F%2Fimg3.doubanio.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664935370&t=d4bf3e4d352c277a1bdebfcc8fda959f'
        },
        {
          url: 'https://img1.baidu.com/it/u=2911909188,130959360&fm=253&fmt=auto&app=138&f=JPEG?w=440&h=641'
        },
        {
          url: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg3.doubanio.com%2Fview%2Fphoto%2Fm%2Fpublic%2Fp2650049201.jpg&refer=http%3A%2F%2Fimg3.doubanio.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664935370&t=d4bf3e4d352c277a1bdebfcc8fda959f'
        },
        {
          url: 'https://img1.baidu.com/it/u=2911909188,130959360&fm=253&fmt=auto&app=138&f=JPEG?w=440&h=641'
        },
        {
          url: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg3.doubanio.com%2Fview%2Fphoto%2Fm%2Fpublic%2Fp2650049201.jpg&refer=http%3A%2F%2Fimg3.doubanio.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664935370&t=d4bf3e4d352c277a1bdebfcc8fda959f'
        },
        {
          url: 'https://img1.baidu.com/it/u=2911909188,130959360&fm=253&fmt=auto&app=138&f=JPEG?w=440&h=641'
        },
        {
          url: 'https://img1.baidu.com/it/u=2911909188,130959360&fm=253&fmt=auto&app=138&f=JPEG?w=440&h=641'
        }
      ],
      addList: [
        {
          url: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg3.doubanio.com%2Fview%2Fphoto%2Fm%2Fpublic%2Fp2650049201.jpg&refer=http%3A%2F%2Fimg3.doubanio.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664935370&t=d4bf3e4d352c277a1bdebfcc8fda959f'
        },
        {
          url: 'https://img1.baidu.com/it/u=2911909188,130959360&fm=253&fmt=auto&app=138&f=JPEG?w=440&h=641'
        },
        {
          url: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg3.doubanio.com%2Fview%2Fphoto%2Fm%2Fpublic%2Fp2650049201.jpg&refer=http%3A%2F%2Fimg3.doubanio.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664935370&t=d4bf3e4d352c277a1bdebfcc8fda959f'
        },
        {
          url: 'https://img1.baidu.com/it/u=2911909188,130959360&fm=253&fmt=auto&app=138&f=JPEG?w=440&h=641'
        },
        {
          url: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg3.doubanio.com%2Fview%2Fphoto%2Fm%2Fpublic%2Fp2650049201.jpg&refer=http%3A%2F%2Fimg3.doubanio.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664935370&t=d4bf3e4d352c277a1bdebfcc8fda959f'
        },
        {
          url: 'https://img1.baidu.com/it/u=2911909188,130959360&fm=253&fmt=auto&app=138&f=JPEG?w=440&h=641'
        },
        {
          url: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg3.doubanio.com%2Fview%2Fphoto%2Fm%2Fpublic%2Fp2650049201.jpg&refer=http%3A%2F%2Fimg3.doubanio.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664935370&t=d4bf3e4d352c277a1bdebfcc8fda959f'
        },
        {
          url: 'https://img1.baidu.com/it/u=2911909188,130959360&fm=253&fmt=auto&app=138&f=JPEG?w=440&h=641'
        },
        {
          url: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg3.doubanio.com%2Fview%2Fphoto%2Fm%2Fpublic%2Fp2650049201.jpg&refer=http%3A%2F%2Fimg3.doubanio.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664935370&t=d4bf3e4d352c277a1bdebfcc8fda959f'
        },
        {
          url: 'https://img1.baidu.com/it/u=2911909188,130959360&fm=253&fmt=auto&app=138&f=JPEG?w=440&h=641'
        },
        {
          url: 'https://img1.baidu.com/it/u=2911909188,130959360&fm=253&fmt=auto&app=138&f=JPEG?w=440&h=641'
        }
      ],
      bottomMain: true
    }
  },
  methods: {
    scrollFun (e) {
      console.log(3333)
      const offsetHeight = e.target.offsetHeight
      const scrollHeight = e.target.scrollHeight
      const scrollTop = e.target.scrollTop
      if (scrollHeight - (offsetHeight + scrollTop) < 10) {
        if (this.bottomMain) {
          this.bottomMain = false
          // this.addListDataFun()
          console.log('到底了开始加载数据')
          setTimeout(() => {
            this.pbList = this.pbList.concat(this.addList)
            this.bottomMain = true
            this.$nextTick(() => {
              this.$refs.compList.waterFall('#tabContainer', '.tab-item')
            })
          }, 300)
        }
      }
    }
  }
}
</script>

<style scoped>
.list-box {
  position: relative;
  width: 100%;
  height: calc(100vh - 240px);
  background: white;
  padding: 20px 30px 20px 20px;
  margin-top: 20px;
  box-sizing: border-box;
  overflow: auto;
}
</style>
