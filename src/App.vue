<script>
import Flipbook from 'flipbook-vue'
import testImg1 from '@/img/01.jpg'
import testImg2 from '@/img/02.jpg'
import testImg3 from '@/img/03.jpg'
import testImg4 from '@/img/04.jpg'
import testImg5 from '@/img/05.jpg'
import testImg6 from '@/img/06.jpg'
import testImg7 from '@/img/07.jpg'
import testImg8 from '@/img/08.jpg'
import testImg9 from '@/img/09.jpg'
import testImg10 from '@/img/10.jpg'
import testImg11 from '@/img/11.jpg'
import testImg12 from '@/img/12.jpg'
import testImg13 from '@/img/13.jpg'
import testImg14 from '@/img/14.jpg'
import testImg15 from '@/img/15.jpg'
import testImg16 from '@/img/16.jpg'
import testImg17 from '@/img/17.jpg'
import testImg18 from '@/img/18.jpg'
import testImg19 from '@/img/19.jpg'
import testImg20 from '@/img/20.jpg'
import testImg21 from '@/img/21.jpg'
import testImg22 from '@/img/22.jpg'
import testImg23 from '@/img/23.jpg'
import testImg24 from '@/img/24.jpg'
import testImg25 from '@/img/25.jpg'
import testImg26 from '@/img/26.jpg'



import axios from 'axios';

import { ref , onMounted , watch } from 'vue';
import { computed } from 'vue'
import { reactive } from 'vue'
export default {
  components: { 
    Flipbook
   },
  setup(props) {
    const pagesData = ref([null])
    const pagesHiRes = ref([null])
    console.log(pagesData);


    pagesData.value.push(testImg1)
    pagesData.value.push(testImg2)
    pagesData.value.push(testImg3)
    pagesData.value.push(testImg4)
    pagesData.value.push(testImg5)
    pagesData.value.push(testImg6)
    pagesData.value.push(testImg7)
    pagesData.value.push(testImg8)
    pagesData.value.push(testImg9)
    pagesData.value.push(testImg10)
    pagesData.value.push(testImg11)
    pagesData.value.push(testImg12)
    pagesData.value.push(testImg13)
    pagesData.value.push(testImg14)
    pagesData.value.push(testImg15)
    pagesData.value.push(testImg16)
    pagesData.value.push(testImg17)
    pagesData.value.push(testImg18)
    pagesData.value.push(testImg19)
    pagesData.value.push(testImg20)
    pagesData.value.push(testImg21)
    pagesData.value.push(testImg22)
    pagesData.value.push(testImg23)
    pagesData.value.push(testImg24)
    pagesData.value.push(testImg25)
    pagesData.value.push(testImg26)

    pagesHiRes.value.push(testImg1)
    pagesHiRes.value.push(testImg2)
    pagesHiRes.value.push(testImg3)
    pagesHiRes.value.push(testImg4)
    pagesHiRes.value.push(testImg5)
    pagesHiRes.value.push(testImg6)
    pagesHiRes.value.push(testImg7)
    pagesHiRes.value.push(testImg8)
    pagesHiRes.value.push(testImg9)
    pagesHiRes.value.push(testImg10)
    pagesHiRes.value.push(testImg11)
    pagesHiRes.value.push(testImg12)
    pagesHiRes.value.push(testImg13)
    pagesHiRes.value.push(testImg14)
    pagesHiRes.value.push(testImg15)
    pagesHiRes.value.push(testImg16)
    pagesHiRes.value.push(testImg17)
    pagesHiRes.value.push(testImg18)
    pagesHiRes.value.push(testImg19)
    pagesHiRes.value.push(testImg20)
    pagesHiRes.value.push(testImg21)
    pagesHiRes.value.push(testImg22)
    pagesHiRes.value.push(testImg23)
    pagesHiRes.value.push(testImg24)
    pagesHiRes.value.push(testImg25)
    pagesHiRes.value.push(testImg26)



    const imgOnload= () =>{
        let loadImg = new Image()
        pagesData.value.forEach(item =>{
            loadImg = new Image()
            if(item !== null){
              loadImg.src = item
            }
        })
    }
    imgOnload()

  





    const herfpage = ref(1)

    const onFlipLeftStart = (page)=> { 
      console.log('flip-left-start', page) 
      if(page === 26){
        herfpage.value = 7
      }
      if(page === 0){
        herfpage.value = 7
      }
    }
    const onFlipRightStart = (page)=> { 
      console.log('flip-right-start', page) 
      if(page === 1){
        herfpage.value = 7
      }
    }
    const onFlipLeftEnd = (page)=>{
      console.log('flip-left-end', page)
      window.location.hash = '#' + page
      herfpage.value =  page
      console.log(herfpage.value);

    }
    const onFlipRightEnd = (page)=>{
      console.log('flip-right-end', page)
      window.location.hash = '#' + page
      herfpage.value =  page
      console.log(herfpage.value);

    }

    
    const onZoomStart = (zoom)=>{
      console.log('zoom-start', zoom)
    }
    const onZoomEnd = (zoom)=>{
      console.log('zoom-end', zoom)    
    }
    const flipbook = ref(null)
    onMounted(()=>{
      console.log(flipbook);



      
      window.addEventListener('keydown', (ev) => {
        console.log(ev.keyCode);
        console.log(flipbook.value);
        // if(ev.keyCode === 37 && flipbook.value.canFlipLeft){
        if(ev.keyCode === 37){
          flipbook.value.flipLeft()
        }
        // if(ev.keyCode === 39 && flipbook.value.canFlipRight){
        if(ev.keyCode === 39 ){
          flipbook.value.flipRight()
        }
      
      
    })
    })






      return{
        pagesData,
        pagesHiRes,
        onFlipLeftStart,
        onFlipRightStart,
        onFlipLeftEnd,
        onFlipRightEnd,
        onZoomStart,
        onZoomEnd,
        herfpage,
        flipbook

        

      }
      
  }
  
}
</script>
<template>
  <!-- <img src="@/images/1.jpg" alt=""> -->
  <!-- <img :src="pagesData[0]" alt=""> -->
  <flipbook class="flipbook"  :data-test="JsonImgRender"
  :pages="pagesData"
  :pagesHiRes="pagesHiRes"
  :perspective="2400"
  :startPage="1"
  :nPolygons="27"
  :zooms="[1,2,4]"
  :gloss="0"
  ref="flipbook"
  @flip-left-start="onFlipLeftStart"
  @flip-right-start="onFlipRightStart"
  @flip-left-end="onFlipLeftEnd"
  @flip-right-end="onFlipRightEnd"
  @zoom-start="onZoomStart"
  @zoom-end="onZoomEnd"

  v-slot="flipbook"
  >
  <div class="btnContainer">
    <button 
    :class="['PreviousBtn', {'disable': !flipbook.canFlipLeft}]" 
    @click="flipbook.flipLeft">上一頁</button>

    <button 
    :class="['PlusBtn', {'disable': !flipbook.canZoomIn}]" 
    @click="flipbook.zoomIn">
    放大<span>(+)</span>
  </button>

    <span class="page-num">
      <span class="title">Page</span>
      <span> {{ flipbook.page }} / {{ flipbook.numPages }}</span>
    </span>
    <button 
    :class="['MinusBtn', {'disable': !flipbook.canZoomOut}]" 
    @click="flipbook.zoomOut">縮小<span>(-)</span></button>
    <button 
    :class="['NextBtn', {'disable': !flipbook.canFlipRight}]" 
    @click="flipbook.flipRight">下一頁</button>
  </div>


  
  <div class="txtcontainer" v-show="herfpage === 1">
    <ul>
      <a target="_blank" href="https://www.instagram.com/ringo.tw/?hl=zh-tw">Instagram<span>ringo.tw</span></a>
      <a target="_blank" href="https://www.facebook.com/ringo2218">Facebook<span>ringo2218</span></a>
      <a target="_blank" href="https://www.twitch.tv/ringo2218">Twitch<span>ringo2218</span></a>
      <a target="_blank" href="https://www.furuke.com/ringo2218">furuke<span>ringo2218</span></a>
    </ul>
  </div>
  <div class="txtcontainer" v-show="herfpage === 26">
    <ul>
      <a target="_blank" href="https://www.instagram.com/ringo.tw/?hl=zh-tw">Instagram<span>ringo.tw</span></a>
      <a target="_blank" href="https://www.facebook.com/ringo2218">Facebook<span>ringo2218</span></a>
      <a target="_blank" href="https://www.twitch.tv/ringo2218">Twitch<span>ringo2218</span></a>
      <a target="_blank" href="https://www.furuke.com/ringo2218">furuke<span>ringo2218</span></a>
    </ul>
  </div>

  </flipbook>





</template>


<style lang="scss">
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  list-style-type: none;
  
}
body{
  background-color: #222;
  overflow: hidden;
}


.flipbook {
  // border: 1px solid #FFF;
  margin: auto;
  width: 90vw;
  height: 90vh;
  // box-shadow: 0 0 20px #000;
}
.flipbook .viewport {
  // border: 1px solid #F00;
  margin-top: 3vh;
  width: 90vw !important;
  height: calc(100vh - 50px - 40px) !important;
}
.flipbook .bounding-box {
  box-shadow: 0 0 20px #000;
}
.btnContainer{
  // border: 1px solid #FFF;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  user-select: none; 
  button{
      max-width: 200px;
      width: 20vw;
      padding: 7px;
      margin: 0px 5px;
      margin-top: 3px;
    }

  .page-num{
    color: #FFF;
    display: inline-block;
    text-align: center;
    max-width: 200px;
    width: 20vw;

    .title{
      display: block;
      margin-top: 7px;
      margin-bottom: 7px;
    }    
  }

}
.txtcontainer{
  position: absolute;
  top: 90%;
  left: 10%;
  transform: translate(-10%,-90%);
  z-index: 999;
  // background: ;
  border: 1px solid #ffffff78;
  user-select: none; 
  
  ul{
    a{
      width: 18vw;
      display: block;
      font-size: 1.8vw;
      color: #FFF;
      position: relative;
      margin: 1vw;
      text-decoration: none;
      span{
        position: absolute;
        right: 0;
        
        color: #FFF;
      }


    }
  }


}
.PreviousBtn,.NextBtn,.PlusBtn,.MinusBtn{
  // font-size: 9px;
  &.disable{
    opacity: 0.3;
  }
}


@media screen and (max-width: 920px) {
.txtcontainer{
  top: 7%;
  left: 50%;
  transform: translate(-50%,-7%);
  ul{
    a{
      width: 25vw;
      display: block;
      font-size: 1.8vw;
      color: #FFF;
      position: relative;
      margin: 1vw;
      text-decoration: none;
      span{
        position: absolute;
        right: 0;
        
        color: #FFF;
      }


    }
  }


}

}

@media screen and (max-width: 540px) {
.txtcontainer{
  border: transparent;
  position: relative;
  top: 0;
  ul{
    position: absolute;
    top: 10px;
    align-items: center;
    display: flex;
    a{
      width: 20vw;
      padding: 3px;
      border: 1px solid #FFF;
      text-align: center;
      height: 30px;
      line-height: 25px;

      span{
        display: none;
      }
      &:nth-child(1){
        position: relative;
        &::before{
          content: url("~@/href/instagram.png");
          position: absolute;
          top: 50%;
          left: -5px;
          transform: translateY(-50%) scale(0.4);
          
          
        }
      }
      &:nth-child(2){
        position: relative;
        &::before{
          content: url("~@/href/facebook.png");
          position: absolute;
          top: 50%;
          left: -5px;
          transform: translateY(-50%) scale(0.4);
          
        }
      }
      &:nth-child(3){
        position: relative;
        &::before{
          content: url("~@/href/twitch.png");
          position: absolute;
          top: 50%;
          left: -5px;
          transform: translateY(-50%) scale(0.4);
          
        }
      }
      &:nth-child(4){
        position: relative;
        &::before{
          content: url("~@/href/furuke.png");
          position: absolute;
          top: 50%;
          left: -5px;
          transform: translateY(-50%) scale(0.4);
          
        }
      }


    }
  }


}

}

@media screen and (max-width: 415px) {
  .txtcontainer{
    ul{
      a{
        &:nth-child(1){
          padding-left: 21px;
          text-align: left;
        }
        &:nth-child(2){
          padding-left: 21px;
          text-align: left;
        }
        &:nth-child(3){
          text-align: left;
          padding-left: 30px;
        }
        &:nth-child(4){
          text-align: left;
          padding-left: 30px;
        }
      }
    }
  }
  .PreviousBtn,.NextBtn,.PlusBtn,.MinusBtn{
  font-size: 9px;
  &.disable{
    opacity: 0.3;
  }
}
}

@media screen and (max-width: 300px) {
  .txtcontainer{
    ul{
      a{
        &:nth-child(1){
          padding-left: 0;
          text-align: center;
          &::before{
            display: none;
          }
        }
        &:nth-child(2){
          padding-left: 0;
          text-align: center;
          &::before{
            display: none;
          }
        }
        &:nth-child(3){
          padding-left: 0;
          text-align: center;
          &::before{
            display: none;
          }
        }
        &:nth-child(4){
          padding-left: 0;
          text-align: center;
          &::before{
            display: none;
          }
        }
      }
    }    
  }
}
</style>