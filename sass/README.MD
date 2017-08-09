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
