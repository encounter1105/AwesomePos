<template>
  <div class="pos">
    <div>
      <el-row>
        <el-col :span="7" class="pos-order" id="order-list">
          <el-tabs>
            <el-tab-pane label="点餐">
              <el-table :data="tableData" border style="width:100%">
                <el-table-column prop="goodsName" label="商品名称"></el-table-column>
                <el-table-column prop="count" label="数量" width="50"></el-table-column>
                <el-table-column prop="price" label="金额" width="70"></el-table-column>
                <el-table-column  label="操作" width="100" fixed="right" >
                  <template slot-scope="scope">
                    <el-button type="text" size="small">删除</el-button>
                    <el-button type="text" size="small">增加</el-button>
                  </template>
                </el-table-column>
              </el-table>
              <div class="div-btn">
                <el-button type="warning">挂单</el-button>
                <el-button type="danger">删除</el-button>
                <el-button type="success">结账</el-button>
              </div>
            </el-tab-pane>
            <el-tab-pane label="挂单">
              挂单
            </el-tab-pane>
            <el-tab-pane label="外卖">
              外卖
            </el-tab-pane>
          </el-tabs>

        </el-col>
        <el-col :span="17">
          <div class="often-goods">
            <div class="title">常用商品</div>
            <div class="often-goods-list">
              <ul>
                <li v-for="goods in oftenGoods">
                  <span>{{ goods.goodsName }}</span>
                  <span class="price">{{ goods.price }}</span>
                </li>
              </ul>
            </div>
          </div>
          <div class="goods-type">
            <el-tabs>
              <el-tab-pane label="汉堡">
                <div>
                  <ul class='cookList'>
                    <li v-for="goods in type0Goods">
                      <span class="foodImg"><img :src="goods.goodsImg" width="100%"></span>
                      <span class="foodName">{{ goods.goodsName }}</span>
                      <span class="foodPrice">{{ goods.price }}</span>
                    </li>
                  </ul>
                </div>
              </el-tab-pane>
              <el-tab-pane label="小食">
                <el-col :span="17">
                  3333333333333333333333333333333
                  <div>
                    <div class="enterpriseGovernMessage">
                      <!--<ul v-for="MessageItems in MessageList" :key="MessageItems.id" :model="detail" class="enterpriseGovernMessage">-->
                        <!--<li v-for="(item,index) in MessageItems.messageList">-->
                          <!--<div v-if="0 === 0" class="user-part">-->
                            <!--问你111111111111112222-->
                            <!--<span class="text-purple">问:</span>-->
                            <!--<p class="m-t-sm answer-txt">-->
                              <!--你是谁?-->
                            <!--</p>-->
                            <!--&lt;!&ndash;LjTODO&ndash;&gt;-->
                            <!--<el-button :key="item.id" class="mui-btn mui-btn-answer mui-btn-sm m-r" @click="reply(item.id)">-->
                              <!--&lt;!&ndash;回复&ndash;&gt;-->
                              <!--&lt;!&ndash;</el-button>&ndash;&gt;-->
                              <!--<el-button-->
                                <!--v-show="nowId===item.id"-->
                                <!--type="button"-->
                                <!--class="mui-btn mui-btn-primary1 mui-btn-outlined mui-btn-xs mui-pull-right"-->
                                <!--@click="askBusWithParent(item.id)"-->
                              <!--&gt;-->
                                <!--保存-->
                              <!--</el-button>-->
                              <!--<el-input v-show="nowId===item.id" v-model="userAskMsgParent" type="textarea" class="m-b-none" name="" cols="30" rows="5" placeholder="请输入您的问题"/>-->
                            <!--</el-button>-->
                          <!--</div>-->
                          <!--<div v-else class="business-part">-->
                            <!--<p>-->
                              <!--<span class="tag tag-success tag-fill">本人</span>-->
                              <!--<span class="m-r-xs name"/>-->
                              <!--<span class="text-purple">回复:</span>-->
                            <!--</p>-->
                            <!--<div class="m-t-sm answer-txt">-->
                              <!--我是前端-->
                              <!--<p>2020/2/23</p>-->
                            <!--</div>-->
                          <!--</div>-->
                        <!--</li>-->
                      <!--</ul>-->
                      <ul>
                        <li>
                          你是？
                        </li>
                        <span>
                          <button :key="2" @click="huifu">
                          回复
                            <el-form>
                              <el-input v-show="key===curentkey" type="textarea" v-model="userAskMsgParent">hi，我来啦</el-input>
                              <button v-show="key===curentkey" @click="baocun">保存</button>
                            </el-form>
                          {{ userAskMsgParent3232 }}
                          </button>
                        </span>
                        <li>
                          我是小可爱
                        </li>
                        <li>
                          我也是小可爱
                        </li>
                      </ul>
                    </div>

                  </div>

                </el-col>
              </el-tab-pane>
              <el-tab-pane label="饮料">饮料</el-tab-pane>
              <el-tab-pane label="套餐">套餐</el-tab-pane>
            </el-tabs>

          </div>
        </el-col>
      </el-row>
    </div>

  </div>
</template>

<script>
 export default {
      name: "Pos",
      data(){
        return{
          curentkey: 2,
          key:2,
          flag:false,
          tableData:[{
            goodsName: '可口可乐',
            price: 8,
            count:1
          }, {
            goodsName: '香辣鸡腿堡',
            price: 15,
            count:1
          }, {
            goodsName: '爱心薯条',
            price: 8,
            count:1
          }, {
            goodsName: '甜筒',
            price: 8,
            count:1
          }],
          oftenGoods:[
            {
              goodsId:1,
              goodsName:'香辣鸡腿堡',
              price:18
            }, {
              goodsId:2,
              goodsName:'田园鸡腿堡',
              price:15
            }, {
              goodsId:3,
              goodsName:'和风汉堡',
              price:15
            }, {
              goodsId:4,
              goodsName:'快乐全家桶',
              price:80
            }, {
              goodsId:5,
              goodsName:'脆皮炸鸡腿',
              price:10
            }, {
              goodsId:6,
              goodsName:'魔法鸡块',
              price:20
            },{
              goodsId:7,
              goodsName:'可乐大杯',
              price:10
            }, {
              goodsId:8,
              goodsName:'雪顶咖啡',
              price:18
            }, {
              goodsId:9,
              goodsName:'大块鸡米花',
              price:15
            }, {
              goodsId:20,
              goodsName:'香脆鸡柳',
              price:17
            }
          ],
          type0Goods:[
            {
              goodsId:1,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg",
              goodsName:'香辣鸡腿堡',
              price:18
            }, {
              goodsId:2,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg",
              goodsName:'田园鸡腿堡',
              price:15
            }, {
              goodsId:3,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos004.jpg",
              goodsName:'和风汉堡',
              price:15
            }, {
              goodsId:4,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos003.jpg",
              goodsName:'快乐全家桶',
              price:80
            }, {
              goodsId:5,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos003.jpg",
              goodsName:'脆皮炸鸡腿',
              price:10
            }, {
              goodsId:6,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos004.jpg",
              goodsName:'魔法鸡块',
              price:20
            }, {
              goodsId:7,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg",
              goodsName:'可乐大杯',
              price:10
            }, {
              goodsId:8,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos003.jpg",
              goodsName:'雪顶咖啡',
              price:18
            },{
              goodsId:9,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg",
              goodsName:'大块鸡米花',
              price:15
            }, {
              goodsId:20,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg",
              goodsName:'香脆鸡柳',
              price:17
            }
          ],
          MessageList:{
          },
          userAskMsgParent: '',
          userAskMsgParent3232: null
        }
      },
      mounted:function(){
          var orderHeight = document.body.clientHeight;
          // console.log(orderHeight);
          // document.getElementById('order-list').style.height = orderHeight+'px';
      },
      methods:{
        huifu(){
          this.key = 2
          if(this.key === this.curentkey){
            console.log(3333333)
          }else{
            console.log(5555555)
          }
        },
        baocun(){
          // this.userAskMsgParent = 2
          this.userAskMsgParent3232 = this.userAskMsgParent + '成功'
          console.log(this.userAskMsgParent3232)
        }
      }

    }
</script>

<style scoped>
.pos-order{
  background-color: #F9FAFC;
  border-right:1px solid #C0CCDA;
}
.div-btn{
  margin-top:10px;
}
.title{
  height:20px;
  border-bottom:1px solid #D3dce6 ;
  background-color: #F9FAFC;
  padding:10px;
  text-align:left;
  }
.often-goods-list ul li{
  list-style:none;
  float:left;
  border:1px solid #E5E9F2;
  padding:10px;
  margin:10px;
  background-color: #fff;
}
.price{
  color:#58B7FF;
  }
.goods-type{
  clear:both;
}
.cookList li{
  list-style: none;
  width:23%;
  border:1px solid #E5E9F2;
  height: auot;
  overflow: hidden;
  background-color:#fff;
  padding: 2px;
  float:left;
  margin: 2px;

}
.cookList li span{

  display: block;
  float:left;
}
.foodImg{
  width: 40%;
}
.foodName{
  font-size: 18px;
  padding-left: 10px;
  color:brown;

}
.foodPrice{
  font-size: 16px;
  padding-left: 10px;
  padding-top:10px;
}
</style>
