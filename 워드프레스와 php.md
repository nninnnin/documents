ACF에서 정의된 필드가 어떻게 렌더링되는가?



어떻게든 

`wp-content/themes/rebel9-2019/page.php` 

가 포스트를 그려내는 부분이라는 것을 알았다.

거기에서는..

`have_posts()`

`the_post()`

`get_template_part('template-parts/content', 'page')`

등의 함수를 사용하는 것을 발견했고 마지막 구문을 통해 경로를 검색해서 아래 파일을 발견.



`wp-content/themes/rebel9-2019/template-parts/content-page.php` 

이 파일에서도

`the_ID()` : is a WordPress function that gets the current post's ID.

`post_class()`: Adds CSS classes

`the_content()`

등 알 수 없는 함수들을 발견..



---



#### 전략.

페이지 데이터를 가져오는 부분은 로컬에서 테스트하고 그대로 붙여넣는다.

스타일링만 메인에서 실시간으로..