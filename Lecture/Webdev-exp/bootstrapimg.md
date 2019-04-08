### Bootstrap에서 이미지 사이즈 조절하는 방법

* 12칸이 있다고 생각하고 12의 최대공약수 별로 칸을 나눈다고 생각하면 쉽다.
* ex> col-lg-4 큰 사이즈로 12칸중에 한칸을 차지 총 3개로 나눌수 있다. col-sm-6 두 칸으로 나눌 수 있다. 브라우저 사이즈가 어느정도 작아질 때 까지 두칸으로 보여질수 있다. 

* 그림 폰트 
  ** 링크[fontawesome](https://fontawesome.com/)
  ** bootstrap의 [그래피콘](https://getbootstrap.com/docs/3.3/components/) 이용하기 
  
* 메뉴 상단 고정하기
 ```<nav class="navbar navbar-inverse navbar-fixed-top">```
 
* 웹페이지 Full로 채우지 않기 위해서는 container 클래스를 
 ```
 <div class="container">
      <div class="jumbotron">
      </div>
  </div> 
  ```
