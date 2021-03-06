# 3rd ASGMT

## Spring boot 실습

앞차수의 Spring 환경을 먼저 경험한 후 Spring boot 구축하고 환경설정을 완료하는 실습을 진행한다. Java로도 Config설정이 가능해서 Spring에 비해 편한 것이 장점이다. Eclipse에서 진행하였고 Demo를 돌릴때는 좌측 네비에서 프로젝트명을 우클릭 하여 Run As > Spring Boot App을 선택한다. 

> 1차때 theater라고 임의로 생성한 DB가 연동이 안됐는데 이번에 MySQL Workbench 버전을 8.0에서 6.3이하로 변경하여 진행했고, DB 관련 부분이 문제없이 실행되었다. 

> 여러 SW 다운로드에서 xxx-RC처럼 적힌것은 Release Candidate의 약자이고 정식배포와 베타버전 사이의 버전이라고 볼 수 있다.

![微信截图_20210820185552](/settingweb_boot/assets/微信截图_20210820185552.png)

위와같이 테스트도 잘 동작한다. 

## MariaDB 연결하기 

1차때도 했지만 `localhost`에서 `mysql -u [username] -p[password]`입력하여 MariaDB에 연결한다. 특정 호스트에서 MariaDB server연결할때는 위 명령어에서 뒤에 `-h [hostname]`을 붙인다. 

### MariaDB server에서 특정 database 연결하기

`mysql -u [username] -p[password] -h [hostname] database_name` 과 같이 입력한다. 

### MySQL Workbench에서 Query문 작성

[여기](https://javakong.tistory.com/67) 참고해서 진행했다. 

## localhost에서 연결을 거부했습니다. 

우선 예를 들면, 127.0.0.1:8080로 바꿔 시도해본다. 만약 localhost:8080 등과 같이 거부당하면 방화벽 문제가 아니고 다른 곳에서 문제가 발생한 경우이다. `src/main/resources/application.properties`를 다시 확인한다. 이번엔 중간에 하나가 오타가 있어서 거부당한것으로 보인다. 수정해주니 정상적으로 접속되었다. [여기](https://achillestendon.tistory.com/35)를 참고해도 좋을듯하다. 

![微信截图_20210820211302](/settingweb_boot/assets/微信截图_20210820211302.png)

위와같이 제대로 출력되는것을 볼 수 있다. 

---

# 4th ASGMT

3차 과제에서 sql문 작성을 누락해서 이번 과제에서 한번에 구현하였다. DB학습에 오래걸려서 시간이 부족하여 우선 결과부터 첨부하고 계속해서 API문서를 수정할 예정이다. 공휴일 제외 월 접속자수를 뿌리는 쿼리문에서 정상적으로 반영되지 않는 오류가 있어서 현재 해결중이다.

![연도별접속자수](/settingweb_boot/assets/연도별접속자수.png)![월별접속자수](https://i.imgur.com/FrUhPN8.png)![부서별월접속자수](https://i.imgur.com/807KN6j.png)![일별접속자수](https://i.imgur.com/sjVAGKk.png)![일평균접속자수](https://i.imgur.com/BHdY56J.png)![공휴일제외월접속자수-수정필](https://i.imgur.com/cLFrH7F.png)

위에서부터 연도별 접속자수, 월별 접속자수, 부서별 월 접속자수, 일별 접속자수, 일평균 접속자수, 공휴일을 제외한 월접속자수를 나타낸다. 