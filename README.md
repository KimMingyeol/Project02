# 몰입캠프 2주차 여행 계획 앱 Traveler
## 팀원
김민결, 차다윤
## ABSTRACT
여러 친구들과 함께 여행을 갈 때, 모든 사람의 의견이 반영될 수 있는 계획을 짜는 것은 힘든 일이다.  
Traveler는 여러 사람이 함께 여행 계획을 편리하게 짤 수 있도록 도와주는 앱이다.

## FUNCTION
### 카카오톡 로그인 기능
- 로고 추가하고 화면 넣기
- 카카오톡 sdk를 이용하여 별도의 회원가입 없이 바로 카카오톡으로 로그인 되는 기능을 구현하였다.
- 한번 로그인한 이후에는 다시 카카오톡 인증창을 거치지 않는다. 

### 여행 계획
홈 화면             |  계획 상세 화면             |  일정 넘기는 화면
:-------------------------:|:-------------------------:|:-------------------------:
<img src="https://user-images.githubusercontent.com/68413811/148860452-6d1b7485-cdaa-49a5-bc13-48eb33a5b242.jpg"  width="270" height="600"/>  |  <img src="https://user-images.githubusercontent.com/68413811/148860805-9c988307-f7dd-47b8-a220-fd7d6b4e54da.jpg"  width="270" height="600"/>  |  <img src="https://user-images.githubusercontent.com/68413811/148861327-cc0220f1-89df-4044-b632-b595daedab98.jpg"  width="270" height="600"/>


#### 홈 화면
- 내가 참여한 여행 계획들을 모아볼 수 있는 홈화면
- 여행 제목, 장소, 날짜, 참여인원, 여행 상태를 볼 수 있음
- 오른쪽 아래 floating button을 통해 계획 추가 가능

#### 계획 상세 화면
- 홈 화면에서 특정 계획을 클릭하여 상세 화면을 띄울 수 있음
- 상세 화면에서는 지도, 날짜 별 일정 목록을 볼 수 있음
- 일정 목록은 날짜 별로 페이지가 있어, 넘겨서 각 날짜의 일정을 따로 관리할 수 있음. (View Pager2와 Recycler View를 함께 사용)

#### 계획 상세 화면 - 일정
일정 추가 화면 1             |  일정 추가 화면 2             
:-------------------------:|:-------------------------:
<img src="https://user-images.githubusercontent.com/68413811/148861687-494414f2-81b0-482b-a441-df9581a092c6.jpg"  width="270" height="600"/>  |  <img src="https://user-images.githubusercontent.com/68413811/148861712-e2ecaf31-db4d-4f4f-8cba-f3c837fb0376.jpg"  width="270" height="600"/>
- 일정 추가하기 버튼을 누르면 화면 1과 같이 직접 제목과 주소를 입력하여 일정을 추가할 수 있음.
- 지도의 마커를 누르면 화면 2와 같이 해당 위치에 대한 일정을 추가할 수 있음
- 일정에는 추가적으로 일정에 필요한 돈과 간단한 메모를 입력할 수 있음

일정 추가 화면 3             |  일정 추가 화면 4             |  시간 선택 화면
:-------------------------:|:-------------------------:|:-------------------------:
<img src="https://user-images.githubusercontent.com/68413811/148862285-1e71492d-9332-4e0f-a76c-8e2f7bcef4b4.jpg"  width="270" height="600"/>  |  <img src="https://user-images.githubusercontent.com/68413811/148862727-cb4f3a55-1174-4ae9-b98c-873d79496b3f.jpg"  width="270" height="600"/>  |  <img src="https://user-images.githubusercontent.com/68413811/148861735-c7cc40aa-d3d7-4f57-9ef0-be6fd93b72ca.jpg"  width="270" height="600"/>
- 이미 추가된 일정들과 시간이 겹치면 화면 3과 같이 토스트 메세지가 뜨고 해당 시간에는 일정을 추가할 수 없음.
- 일정을 추가하거나 수정하면, 자동으로 그림 4와 같이 일정이 시간 순으로 정렬됨 (지도 3과 같은 일정에서 '이동하기' 일정을 추가한 것
- 시간을 누르면 타임 피커를 통해 시간을 선택할 수 있고, 시작시간이 종료시간보다 늦도록 선택할 수 없음

#### 계획 상세 화면 - 지도
지도 1             |  지도 2             |  지도 3
:-------------------------:|:-------------------------:|:-------------------------:
<img src="https://user-images.githubusercontent.com/68413811/148862151-56bff3f5-7f69-4641-be40-6aad0225177e.jpg"  width="270" height="600"/>  |  <img src="https://user-images.githubusercontent.com/68413811/148862355-a6a0254e-1a01-4d5e-be86-a0711e8640f2.jpg"  width="270" height="600"/>  |  <img src="https://user-images.githubusercontent.com/68413811/148862415-b292f613-de88-4deb-82c5-e33a31b81ff3.jpg"  width="270" height="600"/>
- Google Cloud Platform의 Maps SDK와 Places API를 사용함.
- 아래 일정 칸에 들어있는 파란색 마커를 누르면, 지도 1의 사진처럼 해당 위치로 지도가 이동하고 빨간색 마커가 찍힘.
- 지도 2의 사진처럼 스피너에서 레스토랑, 카페 등 원하는 종류를 누르면 지도에 표시된 마커들의 위치가 해당 종류의 위치들로 변경됨
- 지도 3의 사진처럼 내가 추가한 일정의 경로가 빨간색 선으로 지도에 표시 됨.


#### 삭제 기능
일정 삭제 화면             |  계획 삭제 화면             
:-------------------------:|:-------------------------:
<img src="https://user-images.githubusercontent.com/68413811/148861830-c60a1a5c-5c53-4cc0-91d3-8f73983584d1.jpg"  width="270" height="600"/>  |  <img src="https://user-images.githubusercontent.com/68413811/148861862-5469cc91-91a7-485f-9efe-ed7380b69a4f.jpg"  width="270" height="600"/> 
- 롱 클릭을 통해 일정과 계획을 삭제할 수 있음
