# 2020 CIEN 중급반 Unity3D 스터디

---

## 대상
 - 간단하게 프로그래밍을 할 수 있는 분들
    - 변수(int, float, double), 조건문(if), 반복문(while, for), 함수(메서드)를 이해하고 있다
 > 프로그래밍을 처음하는 분들은 힘들 수도 있습니다

## 목표
 - 유니티의 기본적인 조작을 할 수 있다
 - 유니티에서 C#을 사용해서 스크립트를 만들고 사용할 수 있다
 - 유니티 물리엔진을 이해하고 사용할 수 있다
    - 강체(Rigidbody): Velocity, Force, Mass, ... 
    - 충돌: Collision, Collider
 - 기초적인 UI를 만들 수 있다
    - 버튼 클릭
    - 씬이동
    - HP바
    - ...
 - 게임의 데이터를 저장하고 불러올 수 있다
 - 유니티를 하면서 발생하는 오류들을 해결할 수 있다
    - 구글, Stackoverflow, Manual, ... 검색 많이 해보기

## 스터디 방식
 > 일주일에 한번(시험기간 제외) / 총 7번 수업
 - 2시간 수업
    - 1시간 30분: 유니티 개념 강의
    - 20분: 실습
    - 10분: 휴식 및 숙제 체크
 - 숙제
    - 매주 10분짜리 숙제가 있을 수 있다
    - 숙제는 남아서 같이하고 가셔도 됩니다!

## 준비해야 할 것
> "Visual Studio Community"와 "Unity 2018.*.* LTS"가 설치된 노트북

#### 설치법: [`PPT`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/%EC%8A%A4%ED%84%B0%EB%94%94%20%EC%A4%80%EB%B9%84.pptx) [`PDF`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/%EC%8A%A4%ED%84%B0%EB%94%94%20%EC%A4%80%EB%B9%84.pdf)

---

## 일정 [`PDF`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/%EC%8A%A4%ED%84%B0%EB%94%94%20%EA%B3%84%ED%9A%8D.pdf) [`PPT`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/%EC%8A%A4%ED%84%B0%EB%94%94%20%EA%B3%84%ED%9A%8D.pptx)

### 1주차. 유니티 시작하기
#### 1주차 스터디 자료: [`PPT`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/1.%20%EC%9C%A0%EB%8B%88%ED%8B%B0%20%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0.pptx) [`PDF`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/1.%20%EC%9C%A0%EB%8B%88%ED%8B%B0%20%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0.pdf)
 - 유니티 소개
 - 유니티 실행
 - 유니티 기본 용어
 - 레이아웃
 - 뷰
 - 조작법
 - 카메라
 - 빈 게임 오브젝트
 - 기본 오브젝트들
 - 책상 만들기
> 책상 만들기는 숙제로 대체 가능

### 2주차. 유니티 스크립트
#### 2주차 스터디 자료: [`PPT`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/2.%20%EC%9C%A0%EB%8B%88%ED%8B%B0%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8.pptx) [`PDF`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/2.%20%EC%9C%A0%EB%8B%88%ED%8B%B0%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8.pdf)
 - 스크립트 개념
    - Start()
    - Update()
    - 이벤트 함수들의 실행 순서
    - Quiz. Class vs Instance
    - public인 변수들
    - Debug.Log
 - 입력 처리
    - Input.GetKey(키코드)
        - \*Key, \*KeyDown, \*KeyUp
    - Input.GetMouseButton(0) // 0: 좌클릭, 1: 우클릭, 2: 중간(휠) 클릭
    - 입력 받아서 플레이어 움직이기
 - Vector3
     - 내적(dot)/외적(cross)
     - 사칙연산
 - struct 주의점
     - Quiz. struct vs class, 복사할 때 value type과 reference type의 동작 방식 
     - `transform.position.x = 2.3f;`가 사실은 `transform.GetPosition().x = 2.3f;`였다! 그래서 미리 컴파일러가 막아준다
 - Translate self/global
 - 처음보는 함수 -> 유니티 Document
 - frame과 deltaTime 
    - framerate independent하다는 것은 무슨 말인가
    - 플레이어를 시간과 비례하도록 움직이기
 - 물체의 이동과 회전
 - 에셋스토어
 - Flappy Bird의 새의 점프 구현하기
    - 계속 점프가 가능해야 함
    - 컴퓨터 성능과 무관해야 함
> Flappy Bird 1(position만 이용해서 점프 구현하기)

#### Flappy Bird Jump 예시: CustomJump.cs
결과: [https://iamgroooooot.github.io/cien-unity-2020/jump-using-position/](https://iamgroooooot.github.io/cien-unity-2020/jump-using-position/)

``` csharp
using UnityEngine;

public class CustomJump : MonoBehaviour
{
    public float jumpPower = 5f; // 점프 Force

    private const float GRAVITY = -9.81f; // 중력 가속도

    private Vector3 vel; // 현재 속도
    private Vector3 acc; // 현재 가속도

    private void Start()
    {
        // 속도 초기화
        vel = Vector3.zero;
        // 중력 설정
        acc = new Vector3(0, GRAVITY, 0);
    }

    void Update()
    {
        // 스페이스바 누르면 점프!
        if (Input.GetKeyDown(KeyCode.Space))
        {
            vel.y = jumpPower;
        }
        
        // 가속도 적용
        vel += acc * Time.deltaTime;

        // 땅으로 떨어지거나 하늘로 날아가지 않습니다
        if(transform.position.y < -0.5f)
        {
            if (vel.y < 0) vel = Vector3.zero;
        }
        else if(transform.position.y > 5)
        {
            if (vel.y > 0) vel = Vector3.zero;
        }

        // 속도만큼 이동시킨다
        transform.Translate(vel * Time.deltaTime);
    }
}
```


### 3주차. 물리 엔진
#### 3주차 스터디 자료: [`PPT`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/3%20%EC%9C%A0%EB%8B%88%ED%8B%B0%20%EB%AC%BC%EB%A6%AC%EC%97%94%EC%A7%84.pptx) [`PDF`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/3%20%EC%9C%A0%EB%8B%88%ED%8B%B0%20%EB%AC%BC%EB%A6%AC%EC%97%94%EC%A7%84.pdf)
 - 물리 엔진이란?
    - 연산 타이밍 - `FixedUpdate()`
 - 강체(Rigidbody) Component
    - 강체의 정의
    - 이동
      - `rb = GetComponent<RigidBody>()`
      - `rb.velocity = new Vector3(0, 1, 0)`
      - `rb.AddForce(0, 500, 0)`
 - 충돌
    - Collider
    - Collision / Trigger
        - Enter, Stay, Exit
 - Flappy Bird를 구현해보기
    - 벽과 충돌하면 "GameOver" 출력
    - 물리 엔진으로 점프 구현
    - GitHub에 gitignore까지 설정해서 올려보기

### 4주차. 프리팹
 - 프리팹
 - 미사일 만들기
 - 미사일 생성하기
    - Instantiate()
 - 적기(Enemy) 만들기
 - 미사일 쏘는 적기 만들기
    - 플레이어가 적기의 미사일에 맞으면 "아야" 출력
> 미사일 쏘는 적기 만들기는 숙제로 대체 가능

### 5주차. 적기 구현 및 적 매니저
- 적기 추가 및 이동
- 적 이동 패턴 처리
- 코루틴, Update, Invoke 비교해보기
    - WaitForSecond() / deltaTime 타이머
- 피격 처리
    - Tag
- 적기 생성 매니저 구현
- 바로 앞에서 멈추는 유도탄 만들기
    - 랜덤으로 생성 됨
    - 3초 후 자동으로 Destroy()
    - 주인공을 추적
> 바로 앞에서 멈추는 유도탄 만들기

### 6주차. 유니티 UI
- UI 구성
    - 캔버스
    - 해상도
    - 앵커
- 텍스트
- 버튼
- 씬(Scene) 이동
    - GameOver씬
- 점수창 만들기
    - 점수 매니저
    
### 7주차. 게임 데이터 관리
- PlayerPref
    - Enum
    - Save
    - Load
- 빌드하기
- 공유

### 특강. Git을 사용한 파일 관리
#### Source Tree 설치법: [`PPT`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/Git%20%ED%8A%B9%EA%B0%95/Source%20Tree%20%EC%84%A4%EC%B9%98%EB%B2%95.pptx) [`PDF`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/Git%20%ED%8A%B9%EA%B0%95/Source%20Tree%20%EC%84%A4%EC%B9%98%EB%B2%95.pdf)
#### Git 특강 자료: [`PPT`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/Git%20%ED%8A%B9%EA%B0%95/Git%20%ED%8A%B9%EA%B0%95(Source%20Tree%20%EC%82%AC%EC%9A%A9%EB%B2%95).pptx) [`PDF`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/Git%20%ED%8A%B9%EA%B0%95/Git%20%ED%8A%B9%EA%B0%95(Source%20Tree%20%EC%82%AC%EC%9A%A9%EB%B2%95).pdf)

> Source Tree로 버전 관리하기

 - Git이 필요한 이유
 - Stage(=Index에 기록)하기
 - Commit하기
 - Remote 추가하기
    - Origin Remote로 GitHub 사용
 - Push하기
 - Clone하기
 - Reset (Soft, Hard, Mixed)
 - Revert
 - Checkout, Detached HEAD
 - 이전 Commit 수정하기
 - Pull / Fetch&Merge하기
 - Branch 만들기
 - Fast Forward Merge하기
 - 3-Way Merge하기
 - 3-Way Merge에서 발생할 수 있는 Conflict 해결하기
   - Visual Studio로 Conflict 해결하는 법
 - Stash로 다양한 문제 해결해보기
   - 오래된 저장소에서 Pull하기
   - 다른 브랜치로 Commit 옮기기
 - .gitignore 파일 설정하기
