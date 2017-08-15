### Navigation Bar
- 讓nav的ul往右靠，取消```ul mr-auto```，改放 ``` ml-auto```
- Fix要在在上面, nav加```.fixed-top```
<br>


##### RWD
- Logo和Brand要排在同一行可以這樣寫，利用span的屬性inline
```
<a class="navbar-brand customBrand" href="#">
    <span><img src="image/logo.svg" alt="logo"><span>
    <span>May Huang</span>
</a>
```
- Logo和Brand垂直置中，flex align-items: center
- Hamburger要改變顏色可以這樣
```
.custom-toggler .navbar-toggler-icon {
  background-image: url("data:image/svg+xml;charset=utf8,%3Csvg viewBox='0 0 32 32' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath stroke='#1e8ba6' stroke-width='2' stroke-linecap='round' stroke-miterlimit='10' d='M4 8h24M4 16h24M4 24h24'/%3E%3C/svg%3E");
}
```

###  @media (max/min-width: 768px)
```
@media (max-width: 768px){
  當螢幕小於768px做這件事
}

@media (min-width: 768px){
  當螢幕大於768px做這件事
}
```
<br>


### banner
-  六角型，arrowDown都是用absolute排列
- padding-top還是margin-top適合？為什麼藍色的格子會下來


- margin 失效？

```
box-shadow: 0px 80px 0px 0px $lightPink inset,
            0px -80px 0px 0px $lightPink inset;
```

### min-height
- 預防當寬度縮小時，內容往下擠就超出height了
- 例子：版面設計為一面式100vh, screen高度縮小時常常內容會凸出邊界造成跑版
- 所以當內容及各邊界更重要不可以犧牲時，就叫犧牲100vh，改為min-height100vh就好了
```
height: 100vh;
min-height: 708px;;
@media screen and (max-width: 576px){
  height: 100vh;
  min-height: auto;
}
```


### iframe 水平置中
- ```display: block; margin: 0 auto;```就可以了


### flexbox 圖片變形
- 用align-self就可以了，看是要flex start 還是middle都可


### FlexSlider2
- 在同一頁顯示多個flexSlider
```
//這是原本的code
$(window).load(function() {
  $('.flexslider').flexslider({
    animation: "slide",
    controlsContainer: $(".custom-controls-container"),
    customDirectionNav: $(".custom-navigation a")
  });
});
```
由此可得知他是呼叫.flexslider，解法是用不同的id去命名
```
$(window).load(function() {
  $('#profolioSlider').flexslider({
    animation: 'slide',
    customDirectionNav: $(".profolioNavigation a")
  });

  $('#demoSlider').flexslider({
    animation: 'slide',
    controlsContainer: $(".demo-controls-container"),
    customDirectionNav: $(".demoNavigation a")
  });
});
```

### 不能改變的Contact From
```
<script src="http://www.powr.io/powr.js" external-type=html></script>
<div class="powr-contact-form" id="8eb10070_1501728824"></div>
```

```
const inputName = document.querySelector('input.form-control');
const inputSubject = document.querySelector('input.user-success');
const inputEmail = document.querySelector('input email');
const inputmessage = document.querySelector('textarea.form-control');
const inputBtn = document.querySelector('#submitButton');

inputName.value = 'teng';
inputSubject.value = 'test';
inputEmail.value = 'coffeealcohol@gmail.com';
inputmessage.value = 'test text area';
realBtn.click();
```


### 能改變的Contact form

- Google雲端
  - 新增 > Google表單 > 右下角有一個？ > 返回舊表單
  - 編輯完後 上面有一個查看回應 點選建立表單
- 點選 *查看即時表單*
  - 開發者模式，從```<div class="ss-form">```開始複製到```</tr></tbody></table></div></ol></form></div>```


- 自訂6~8英文權杖, 例如hahaha
  ```
  <iframe name="iframe_權杖" id="iframe_權杖" style="display:none;" onload="if(typeof sent_權杖!='undefined'){window.location='googleForm.html';}"></iframe>
  ```

- 把上面這一串插在```<div class="ss-form">```後面
- 在iframe後面的form Tag裡，改寫成這樣
```
target="iframe_權杖"
onsubmit="sent_權杖=true"
```
- 當表單填寫完後寄出重回自己的頁面的功能：
```
{window.location='頁面的名稱eg:googleForm.html';}
```


### padding-bottom
- 除了與下一個DOM隔開距離
- 子元素**使用absolute不想被覆蓋**也可以用這招喔


### vh/vw 和 % 傻傻分不清楚

### box-shadow: 0 -100px 0 0 #fff inset;



```
// Function: Demo page appear on Screen
// var triggle = document.querySelector(".demoBtn");
// var demo = document.querySelector(".demo");
// var body = document.querySelector("body")
// var esc = document.querySelector(".escHome");
//
// //Demo Page move to screen
// triggle.addEventListener("click", function(){
//   demo.style.top = "40px";
//   body.style.overflow = "hidden";
//   demo.style.overflow = 'scroll';
//   demo.style.height = '100vh';
//   $('nav').removeClass('nav-up').addClass('nav-down');
// });
//
// //From demo page(Screen) back to main page
// esc.addEventListener("click", function(){
//   demo.style.top = "-2000px";
//   body.style.overflow = "auto";
// });
```

```
pauseOnAction: true,            //Boolean: Pause the slideshow when interacting with control elements, highly recommended.
```

location.reload();
