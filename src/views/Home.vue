<template>
  <div class="home">
    <!-- <div class="wrapper" style="position:relative">
    <div class="tableBox" >
      <div class="showTD">
        <table style="width:80px">
          <thead><th>{{title[0]}}</th></thead>
          </table>
        </div>
      <div class="showTH">
        <table cellspacing="0">
          <thead>
            <th v-for="item in title" :key="item">{{item}}</th>
          </thead>
        </table>
      </div>
      <div class="showCol">
        <table cellspacing="0">
        <thead>
          <th v-for="item in title" :key="item">{{item}}</th>
        </thead>
        <tbody>
            <tr v-for="item in 30" :key="item">
              <td v-for="item in 7" :key="item">{{item}}</td>
            </tr>
        </tbody>
        </table>
      </div>
      <table id="tab" cellspacing="0" >
        <thead>
          <th v-for="item in title" :key="item">{{item}}</th>
        </thead>
        <tbody>
            <tr v-for="item in 30" :key="item">
              <td v-for="item in 7" :key="item">{{item}}</td>
            </tr>
        </tbody>
      </table>
    </div>
    </div> -->
    <Ttable></Ttable>
  </div>
</template>

<script>
// @ is an alias to /src
import Ttable from '@/views/table.vue'

export default {
  name: 'Home',
  components: {
    Ttable
  },
  data(){
    return{
      title:['编号','项目','性别','年龄','电话号码','电子邮箱','家庭住址']
    }
  },
  mounted(){
    // document.querySelector('.tableBox').addEventListener('scroll', function(){
    //   if(this.scrollLeft>0){
    //     document.querySelector('.showCol').classList.add('addShadow');//添加阴影样式
    //   }else{
    //     document.querySelector('.showCol').classList.remove('addShadow');
    //     // this.scrollTo(0,this.scrollTop)
    //   }
    //   if(this.scrollTop<0){
    //     this.scrollTo(this.scrollLeft,0)
    //   }
    //   document.querySelector('.showCol').scrollTo(0,this.scrollTop)
    //   document.querySelector('.showTH').scrollTo(this.scrollLeft,0)
    // })
  }
}
</script>
<style lang="less" scoped>
.home{
  position: relative;

.tableBox{
  width: 95vw;
  height: 300px;
  overflow: auto;
  overflow-x: auto;
  background: #fff;
  box-shadow:3px 3px 10px rgba(204, 204, 204,.3);
  &::-webkit-scrollbar-track-piece {
  background-color: rgba(0, 0, 0, 0);
  }
  &::-webkit-scrollbar {
  width: 6px;
  height: 6px;
  -webkit-border-radius: 5px;
  -moz-border-radius: 5px;
  border-radius: 5px;
  }
  &::-webkit-scrollbar-thumb {
  background-color: rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  -webkit-border-radius: 5px;
  -moz-border-radius: 5px;
  border-radius: 5px;
  min-height: 28px;
  }
  &::-webkit-scrollbar-thumb:hover {
  background-color: rgba(0, 0, 0, 0.5);
  -webkit-border-radius: 5px;
  -moz-border-radius: 5px;
  border-radius: 5px;
  }
  .showTD{
    background: rgb(247, 249, 250);
    width: 80px;
    height: 41px;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 999;
    overflow: hidden;
  }
  .showCol{
  background: #fff;
  height: 300px;
  }
  .showTH{
    background: rgb(247, 249, 250);
    position: absolute;
    top:0;
    left:0;
    z-index: 900;
    width: 95vw;
    height: 41px;
    overflow: hidden;

  }
  .showCol{
    width:80px;
    height:300px;
    position: absolute;
    top:0;
    left:0;
    z-index: 995;
    overflow: hidden;

  }
  table{
    table-layout: fixed;
    border: 0;
    width: 600px;
    th{
        width: 80px;
        padding: 10px 0;
    }
    tr{
      td{
        width: 80px;
        border-bottom: 1px solid rgb(233, 237, 240) ;
        padding: 10px 0;
      }
      &:first-child{
        display: none;
      }
    }
  }
}
  .addShadow{
    box-shadow:0 0 0 #fff,
              3px 3px 10px rgba(204, 204, 204,.3),
              0 0 0 #fff,
              0 0 0 #fff;
  }
}
  
  
</style>
