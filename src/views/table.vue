<template>
  <div class="Ttable">
    <div class="wrapper" style="position:relative;overflow: hidden;height:300px">
      <div class="thBlcok" style="height:41px"></div>
      <div style="display:flex;position:absolute;top:0;left:0;overflow:hidden;width:100%">
        <div style="height:300px;display:inline-block;width:86px;"></div>
        <div class="tableBox">
            <!-- <div style="display:flex"> -->
                <div class="showTD">
                    <table style="width:86px">
                    <thead>
                        <th>{{title[0]}}</th>
                    </thead>
                    </table>
                </div>
                <div class="showTH">
                    <table cellspacing="0">
                    <thead>
                        <th v-for="item in title" :key="item">{{item}}</th>
                    </thead>
                    </table>
                </div>
            <!-- </div> -->
          <div class="showCol">
            <table cellspacing="0">
              <thead>
                <th v-for="item in title" :key="item">{{item}}</th>
              </thead>
              <tbody>
                <tr v-for="item in 30" :key="item">
                  <td>{{item}}</td>
                </tr>
              </tbody>
            </table>
          </div>
          <div style="display:flex;flex-direction:column">
          <!-- <table>
              <thead>
              <th v-for="item in title_two" :key="item">{{item}}</th>
            </thead>
          </table> -->
          <table id="tab" cellspacing="0">
            <thead>
              <th v-for="item in title_two" :key="item">{{item}}</th>
            </thead>
            <tbody>
              <tr v-for="item in 30" :key="item">
                <td v-for="item in 6" :key="item">{{item}}</td>
              </tr>
            </tbody>
          </table>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Ttable",
  data() {
    return {
      title: [
        "编号",
        "项目",
        "性别",
        "年龄",
        "电话号码",
        "电子邮箱",
        "家庭住址"
      ],
      title_two: [
        "项目",
        "性别",
        "年龄",
        "电话号码",
        "电子邮箱",
        "家庭住址"
      ]
    };
  },
  mounted() {
    document.querySelector(".tableBox").addEventListener("scroll", function() {
      if (this.scrollLeft > 0) {
        document.querySelector(".showCol").classList.add("addShadow"); //添加阴影样式
      } else {
        document.querySelector(".showCol").classList.remove("addShadow");
        // this.scrollTo(0, this.scrollTop);
      }
      if (this.scrollTop < 0) {
        this.scrollTo(this.scrollLeft, 0);
      }
      document.querySelector(".showCol").scrollTo(0, this.scrollTop);
      document.querySelector(".showTH").scrollTo(this.scrollLeft, 0);
    });
  }
};
</script>
<style lang="less" scoped>
.Ttable {
  position: relative;
  box-shadow: 0px 0px 18px rgb(219, 219, 219);
  .tableBox {
    width: 312px;
    // flex: 1;
    height: 300px;
    overflow-y: auto;
    overflow-x: auto;
    background: #fff;
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
    .showTD {
      background: rgb(239, 243, 247);
      width: 86px;
      height: 41px;
      position: absolute;
      top: 0;
      left: 0;
      z-index: 999;
      overflow: hidden;
    }
    .showCol {
      background: #fff;
      height: 300px;
    }
    .showTH {
      background: rgb(239, 243, 247);
      position: absolute;
      top: 0;
      left: 0;
      z-index: 900;
      width: 100%;
      height: 41px;
      overflow: hidden;
    }
    .showCol {
      width: 86px;
      height: 300px;
      position: absolute;
      top: 0;
      left: 0;
      z-index: 995;
      overflow: hidden;
    }
    table {
      table-layout: fixed;
      border: 0;
      width: 514px;
      th {
        width: 86px;
        padding: 10px 0;
      }
      tr {
        td {
          width: 86px;
          border-bottom: 1px solid rgb(240, 244, 248);
          padding: 10px 0;
        }
        // &:first-child {
        //   display: none;
        // }
      }
    }
  }
  .addShadow {
    box-shadow: 0 0 0 #fff, 3px 3px 10px rgba(204, 204, 204, 0.3), 0 0 0 #fff,
      0 0 0 #fff;
  }
}
</style>
