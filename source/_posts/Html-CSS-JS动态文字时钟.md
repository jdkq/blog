---
title: Html CSS JS动态文字时钟
categories: Web前端
tags: js小插件
top_img: http://browser9.qhimg.com/bdr/__85/t01c07a94bf0136dd29.jpg
cover: >-
  https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1586260469578&di=77993e59c73755519d7e11237e2dccf8&imgtype=0&src=http%3A%2F%2Fwww.mobiletrain.org%2Fd%2Ffile%2Fabout%2Finfo%2F4bfd0d81f83e36e9b2ca273efeadf474.jpg
abbrlink: 58112
date: 2020-03-30 01:30:27
comments:
hide:
toc:
---
# 演示
[点击演示](/file/timer.html)

# 代码
```
<!DOCTYPE html>
<html lang="en">

<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <meta http-equiv="X-UA-Compatible" content="ie=edge">
   <title>动态时钟</title>
   <style>
      .total {
         position: absolute;
         display: flex;
         justify-content: center;
         align-items: center;
         width: 600px;
         height: 600px;
         font-size: 14px;
      }

      #tier {
         font-weight: 900;
      }

      #shizhong {
         /* background-image: url("./1b18aba6c58fba668715ba20abaed792.jpg"); */
         background-position: center;
         background-size: 100%;
         width: 1500px;
         height: 850px;
         background-repeat: no-repeat;
         display: flex;
         justify-content: center;
         align-items: center;
      }

      * {
         transition: all linear .4s;
      }

      #hours {
         position: absolute;
         top: 50%;
         left: 50%;
         width: 400px;
         height: 400px;
         margin-top: -200px;
         margin-left: -200px;
         border-radius: 50%;
      }

      #mins {
         position: absolute;
         top: 50%;
         left: 50%;
         width: 600px;
         height: 600px;
         margin-top: -300px;
         margin-left: -300px;
         border-radius: 50%;
      }

      #secs {
         position: absolute;
         top: 50%;
         left: 50%;
         width: 800px;
         height: 800px;
         margin-top: -400px;
         margin-left: -400px;
         border-radius: 50%;
      }

      #hours>span,
      .minsEles,
      .secsEles {
         position: absolute;
         width: 100%;
         height: 100%;
         display: flex;
         justify-content: flex-end;
         align-items: center;
      }

      #center1,
      #center2 {
         position: absolute;
         top: 50%;
         left: 50%;
         width: 10px;
         height: 10px;
         margin: 10px 0 0 -5px;
         border-radius: 50%;
         background-color: black;
      }

      #center2 {
         margin: 13px 0 0 0;
         width: 0px;
         height: 2px;
         border-radius: 0;
         transition: all linear 1s;
      }
   </style>
</head>

<body>
   <div id="shizhong">
      <div class="total">
         <div id="tier"></div>
         <div id="hours"></div>
         <div id="mins"></div>
         <div id="secs"></div>
         <span id="center1"></span>
         <span id="center2"></span>
      </div>
   </div>

   <script type="text/javascript">
      var time = new Date();
      var year = time.getFullYear();// 年份
      var month = time.getMonth() + 1;  // 月份
      var date = time.getDate();    // 日期
      var day = time.getDay();      // 周几
      var hour = time.getHours();   // 小时
      var min = time.getMinutes();  // 分钟
      var sec = time.getSeconds();  // 秒数
      // 各位数字  或  者小于十的数字  转换为汉字
      function numbergewei(a) {
         switch (a) {
            case 0: return "零";
            case 1: return "一";
            case 2: return "二";
            case 3: return "三";
            case 4: return "四";
            case 5: return "五";
            case 6: return "六";
            case 7: return "七";
            case 8: return "八";
            case 9: return "九";
         }
      }

      // 数字转换为汉字
      function number(a) {
         if (a >= 10) {
            if (a > 100) {    //    年份
               let str = "";
               for (let i = 1000; i >= 1; i = i / 10) {
                  str += numbergewei(parseInt(a / i % 10));
               }
               return str;
            } else if (a <= 20) {  //  十几
               return "十" + numbergewei(parseInt(a % 10))
            }
            let data = numbergewei(parseInt(a % 10)) == '零' ? "" : numbergewei(parseInt(a % 10))
            return numbergewei(parseInt(a / 10)) + "十" + data;
         }
         return numbergewei(a);
      }

      // 渲染时钟指针
      function renderClock(danwei = "分", findClass = "mins", clases = "minsEles", num = 60) {
         let minsStr = "";
         for (let i = 1; i <= num; i++) {
            if (i == num) {   //    如果分、秒针为60，或时针为24时，给零
               minsStr += `<span class='${clases}'>零${danwei}</span>`;
               break;
            }else if( i % 10 == 0){    // 如果是10的倍数，去掉生成的汉字 “零”  
               if(i ==10){             // 如果是10       去掉生成的汉字 “一”  
               minsStr += `<span class='${clases}'>十${danwei}</span>`;
               }else{
               minsStr += `<span class='${clases}'>${number(i/10)}十${danwei}</span>`;
               }
            }
            else{
            minsStr += `<span class='${clases}'>${number(i)}${danwei}</span>`;
            }
         }
         document.getElementById(findClass).innerHTML = minsStr;
      }

      // 给指针角度
      function minsXuanzhuan(clases = "minsEles", num = 60) {
         let minsEleArr = document.getElementsByClassName(clases);
         for (let i = 0; i < minsEleArr.length; i++) {
            minsEleArr[i].style.transform = `rotate(${i * (360 / num)}deg)`;
         }
      }

      // 旋转
      function xuanzhuan(ele, jiaodu = 60, time = 2) {
         let arr = [];
         for (let i = 0; i < ele.length; i++) {
            let data = ele[i].style.transform.split("(")[1].split("deg")[0] - 0
            data -= (360 / jiaodu) * (time - 1);
            arr.push(data)
         }
         return arr;
      }

      // 根据当前时间排序时钟
      function setClock(sec = 2, secsEle, num = 60) {
         let arr = xuanzhuan(secsEle, num, sec);
         for (let i = 0; i < secsEle.length; i++) {
            secsEle[i].style.transform = `rotate(${arr[i]}deg)`
            if (arr[i] % 360 == 0) {
               secsEle[i].style.fontWeight = `900`
            } else {
               secsEle[i].style.fontWeight = `200`
            }
         }
      }

      // 中间年月日渲染
      function renderYear() {
         let setDey = "日"
         if(day)setDey = number(day);
            document.getElementById("tier").innerHTML = `
      <span class="years">${number(year)}</span>年<span class="months">${number(month)}</span>月<span class="dates">${number(date)}</span>日
      星期<span class="days">${setDey}</span>
      `;
      }

      // 中间横线变长
      setTimeout(() => {
         document.getElementById("center2").style.width = "400px";
      }, 10);

      //    渲染时钟
      renderYear();
      renderClock();
      renderClock("秒", "secs", "secsEles");
      renderClock("时", "hours", "hoursEles", 24)

      let secsEle = document.getElementsByClassName("secsEles");//  秒数节点
      let minsEle = document.getElementsByClassName("minsEles");//  分钟数节点
      let hoursEle = document.getElementsByClassName("hoursEles");//  小时数节点
      setTimeout(() => {
         minsXuanzhuan("hoursEles", 24);  // 散开时针
         setTimeout(() => {
            minsXuanzhuan();              // 散开分针
            setTimeout(() => {
               minsXuanzhuan("secsEles"); // 散开秒针

               setTimeout(() => {
                  let arr = [];
                  time = new Date();
                  hour = time.getHours();   // 小时
                  min = time.getMinutes();  // 分钟
                  sec = time.getSeconds();  // 秒数
                  
                  setClock(sec, secsEle);     // 给秒针时间
                  setClock(min, minsEle);    // 给分针时间
                  setClock(hour, hoursEle, 24);  // 给时针时间
                  // 让时钟走起来
                  setInterval(() => {
                     setClock(2, secsEle);    // 秒针时间给2时，秒针旋转一个刻度
                     time = new Date();
                     if (time.getMinutes() != min) { //     判断是否旋转分针
                        min = time.getMinutes();
                        setClock(2, minsEle);
                        if (time.getHours() != hour) { //   判断是否旋转时针
                           hour = time.getHours();
                           setClock(2, hoursEle, 24);
                           if (time.getDate() != date) {  //    判断日期是否变化
                              date = time.getDate();
                              day = time.getDay();
                              year = time.getFullYear();
                              month = time.getMonth() + 1;
                              renderYear();
                           }
                        }
                     }
                  }, 1000);   // 每秒转动秒针时间
               }, 500);       // 指针对齐时间
            }, 300);          // 秒针散开时间  
         }, 300);             // 分针散开时间
      }, 400);                // 时针散开时间

   </script>
</body>

</html>
```