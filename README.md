# Youtube-Channel-Analysis

유튜브 랭킹 사이트(Noxinfluencer, Utu)에서 데이터를 크롤링하고, 그 데이터를 데이터프레임 형식으로로 변환하여 분석한 프로젝트를 백업한 저장소입니다.

개발 환경과 사용한 라이브러리 및 모듈은 다음과 같습니다.

- 개발 환경
    - Python 3.7.6
    - Jupyter Notebook (Anaconda3)
- 크롤링
    - Selenium
    - BeautifulSoup
- 데이터 분석
    - Pandas
    - Numpy
- 데이터 시각화
    - matplotlib
    - seaborn

## 프로젝트 설명

**자세한 과정과 코드 설명은 :point_right:[report.pdf](https://github.com/dudtjakdl/Youtube-Channel-Analysis/blob/main/report.pdf):point_left: 참고!**

* 현재(2021.07) [utu(우투)](https://utu.kr/rank) 사이트 top100 랭킹에 **해외 유튜버의 데이터가 추가되어** 프로젝트를 실제 수행 했을때(2019.11~2019.12)의 분석 결과와 다릅니다.:sob:

![프로젝트 과정](https://i.ibb.co/7Nx2Q9N/image.png)

1. 데이터 생성
    - DataFrame1 (df1) - [noxinfluencer](https://kr.noxinfluencer.com/youtube-channel-rank/top-100-kr-all-youtuber-sorted-by-subs-weekly/)에서 한국 top100
유튜브채널 정보 크롤링 
    - DataFrame2 (df2) - [utu(우투)](https://utu.kr/rank)에서 한국 top100
유튜브채널 정보 크롤링 
    - DataFrame3 (df3) - df1과 df2 같은 채널명끼리 
항목(column) 병합

2. df3 데이터 추가 및 수정
    - 데이터에 '만', '억'이라 붙어있는 string 값들을 숫자로 변환
    - '총 활동일' 열을 새로 만들어 추가
    - string 타입인 숫자값들을 전부 numeric 타입으로 변환

3. 데이터 분석
    - 실시간 스트리밍(Live) 중인 채널명, 영상 제목, 링크 찾기
    - 각 변수끼리 상관관계 값 구하기
    - 직접 정의한 변수인 '채널 점수' 값 매기기