## Paging

페이지에 대해 설명 잘 해 놓았다.

https://copycode.tistory.com/98?category=740133
https://copycode.tistory.com/102?category=740133
https://copycode.tistory.com/107?category=740133

페이징 TLB 단계에 대해서 설명 잘 해 놓았다.

http://blog.naver.com/PostView.nhn?blogId=qbxlvnf11&logNo=221363771287&parentCategoryNo=&categoryNo=63&viewDate=&isShowPopularPosts=false&from=postView

## 쓰레싱(Thrashing) 

활발하게 사용되는 페이지 집합을 지원해 줄 만큼 프레임을 충분히 할당 받지 못한 프로세스는 페이지 부재가 발생한다. 이 때 페이지 교체가 필요하지만 이미 활발하게 사용되는 페이지들만으로 이루어져 있어 어떤 페이지가 교체 되든지 바로 다시 페이지 교체가 필요하게 된다. 프로세스를 교체를 하면 이 교체 시간이 오버헤드라 cpu의 이용률이 떨어진다. 이걸 보고 운영체제는 cpu이용률을 높이기 위해서 다중 프로그래밍 정도를 더 높인다. 결국 프로세스의 수는 더 많아지며 페이지 폴트도 더 많이 발생하게 되고 운영체제는 계속 더 많은 프로세스를 메모리에 올리려고 한다. 이때 시스템의 처리율은 대단히 낮아지는 이것을 쓰레싱이라 한다. 
