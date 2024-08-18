LCP란, Largest Contentful Paint의 약자로서 웹 바이탈이라 불리우는 3가지 중요한 웹 성능 지표(performance metrics) 중 하나다. 그 이름에서 알 수 있듯, LCP는 화면에 보여지는 커다란 존재감의 이미지 등의 요소가 사용자에게 시각적으로 보여지기까지의 시간을 의미한다.

기본적으로 레벨나인의 웹사이트 rebel9.co.kr은 사무실 와이파이 환경에서 문제 없이, 아주 빠르게 로딩된다.

구글에 의해 작성되는 https://web.dev/articles/optimize-lcp?hl=ko 에 의하면

> 우수한 사용자 환경을 제공하기 위해 **사이트는 페이지 방문의 75% 이상에서 LCP를 2.5초 이하로 유지해야 합니다.**



<img src='/Users/rebel9/Library/Application Support/typora-user-images/스크린샷 2024-08-14 오후 3.56.43.png' style='float:left; width: 30%' /> 사무실에서 연결된 와이파이에서 측정된 결과는 다음과 같다. 몇 번을 시도해도 모두 900ms 대를 유지했다. 그러므로 구글의 기준에 비해 매우 빠른 로딩 속도를 보이는 것.

비교적 느린 인터넷과 CPU 환경을 사용해 다시 측정해 보았다. 재설정된 테스트 환경은 4G (slow), CPU 20배 느리게 (테스트 PC는 M2 pro를 사용 중).





<img src='/Users/rebel9/Library/Application Support/typora-user-images/스크린샷 2024-08-14 오후 4.00.36.png' style='float: right; width: 30%' />재측정 결과는 놀라웠는데, 무려 18초가 걸렸다.

당황스러운 마음으로 CPU와 네트워크 속도를 재설정하여 측정해 본 결과로는 CPU 스로틀링은 거의 의미가 없었고, 네트워크 속도 (4G slow, 4G fast) 조정 시 큰 영향이 있었다.

4G slow로는 대부분 18초대, 4G fast로는 대부분 4초대의 LCP가 측정되었다.

확실히 4초대의 LCP에서는 '조금 느리네' 라는 느낌으로 체감되었다.

LCP를 줄이는 방법은 컨텐츠의 크기를 줄이거나, 중간에 로딩되는 스크립트를 최적화하는 방법이 존재. 먼저 컨텐츠의 크기를 줄이는 것을 시도해본다.