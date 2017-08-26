# test fork

## Navigation Bar
### 位置
- 讓nav的ul往右靠，取消```ul mr-auto```，改放 ``` ml-auto```
- Fix要在在上面, nav加```.fixed-top```


### Logo & Brand
- Logo和Brand垂直置中，flex align-items: center
- Logo和Brand要排在同一行可以這樣寫，利用span的屬性inline
```
<a class="navbar-brand customBrand" href="#">
    <span><img src="image/logo.svg" alt="logo"><span>
    <span>May Huang</span>
</a>
```


### 漢堡設定
- 可以更改顏色等，下方自行參透

```
.navbar-toggler-icon {
  background-image: url("data:image/svg+xml;charset=utf8,
  %3Csvg viewBox='0 0 32 32'
  xmlns='http://www.w3.org/2000/svg'
  %3E%3Cpath stroke='#1e8ba6'
  stroke-width='2' stroke-linecap='round' stroke-miterlimit='10'
  d='M4 8h24M4 16h24M4 24h24'/%3E%3C/svg%3E");
}
```


### navigation bar 選單下拉出問題
- 常常是padding 和  height的問題
<br>




## Home
-  六角型，arrowDown都是用absolute排列
- heading，因為懶得計算absolute的width和margin，故另開一個div 100vh來設display flex，使heading置中．
<br>


## About
### min-height
- 預防當寬度縮小時，內容往下擠就超出height了
- 例子：版面設計為一面式100vh, screen高度縮小時常常內容會凸出邊界造成跑版
- 所以當內容超過邊界時，增加min-height100vh就好了


### title
- 這裡使用margin-top而非padding-top差別在於內容物邊界的判定: 因為垂直置中是用flexbox做的，因此title上面如果是padding，整個content就會偏下．

### flexbox 圖片變形
- 用align-self就可以了，看是要flex start 還是middle都可
<br>


## Profolio
### vh/vw 和 % 傻傻分不清楚
- % 取值是來自父元素的寬度



## Demo
### iframe 水平置中
- ```display: block; margin: 0 auto;```就可以了

### 粉紅框也可以用box-shadow做出來
```
box-shadow: 0px 80px 0px 0px $lightPink inset,
            0px -80px 0px 0px $lightPink inset;
```



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


### 取消自動輪播
```
pauseOnAction: true,            //Boolean: Pause the slideshow when interacting with control elements, highly recommended.
```


## Contact
### 不能改變的Contact From
- 使用```http://www.powr.io/powr.js```
- 如還要更改樣式，自己見一個Form用js把資料傳給powr的form
```
<script src="http://www.powr.io/powr.js" external-type=html></script>
<div class="powr-contact-form" id="8eb10070_1501728824"></div>
```
- Javascrip(參考，有誤)
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


### Google Form，能改變的Contact form

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

- 當要跳到特定位置手機版會有bug
  - 使用location.reload();
  ```
  window.location='index.html#contact'; location.reload();
  ```


### 留空間給Footer
- footer 設absolute bottom:0  
- 父元素設relative 再設padding-bottom
- padding-bottom除了與下一個DOM隔開距離
- 使用absolute的 **子元素不想被覆蓋** 也可以用這招喔






## 其他
###字體問題
- 最好都用google font，否則太特殊的字體不一定每個裝置都有．

###  @media screen
```
@media screen and (max-width: 768px){
  當螢幕小於768px做這件事
}
@media screen and (max-width: 768px){
  當螢幕大於768px做這件事
}
```
