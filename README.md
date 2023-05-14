# 게임 기본 요소 구현 프로젝트 🧩

> 본 프로젝트는 언리얼 엔진을 이용한 게임 개발에 있어 기본이 되는 기능(애니메이션, 충돌 감지, AI) 등을 <br /> 학습하고 실제로 구현하는 것을 목적으로 함



## Tech Stack
<p>
<img src="https://img.shields.io/badge/unrealengine-0E1128?style=for-the-badge&logo=unrealengine&logoColor=white">
<img src="https://img.shields.io/badge/c++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white">
</ p>


## 구현 목록
### 무빙 애니메이션
![움직이는 애니메이션](https://github.com/minhvvan/TestProject/assets/59609086/a543d2a6-650c-4036-b872-4703f57cd7ab)
- Animation Blueprint를 이용하여 Animation을 적용. Ground관련 Animation은 BlendSpace를 이용하여 특정 값에 따라 Animation을 부드럽게 보간하여 출력되게 함. 
- Animation Resource가 부족하여 다른 종류의 Animation으로 대체함. Resource만 있다면 자연스럽게 걷는 Animation적용 가능

### 무기 장착
![무기 장착 공격](https://github.com/minhvvan/TestProject/assets/59609086/4ba741cf-bd91-4006-9c6d-270dbea345c7)
- 무기 Actor에 Triger를 추가하여 Overlap Event를 감지하게 만들었음. Overlap Event가 감지되면 Overlap된 Actor의 지정된 Socket에 무기를 Attach하게 함
- 왼쪽 마우스 클릭에 Attack을 추가하여 공격이 가능하게 만들었음. Actor를 기준으로 조그만한 Capsule범위로 공격 대상을 탐지, 보이는 색깔 Capsule은 디버그용

### 공격 탐지
![공격감지](https://github.com/minhvvan/TestProject/assets/59609086/3945a127-a917-491d-ad67-1dc35ec0e2e1)
- 공격 유효 범위에 적(Actor)가 존재하면 초록색, 그렇지 않으면 빨간색 Capsule을 Draw하게 하였고 Attack이 성공하면 공격받은 대상의 체력을 닳게하였음
- 공격에 맞으면 체력이 줄고 HP Bar가 변함

### AI 탐지
![AI감지](https://github.com/minhvvan/TestProject/assets/59609086/dad07675-971b-4c8f-8c10-eead6a76af67)
- Behavior Tree를 이용하여 적(Actor)의 AI시스템을 구현
- 일정 시간마다 특정 범위를 탐색한 후 적을 발견하면 그 적에게 다가가 공격을 시도하게 하는 Logic을 구현함
