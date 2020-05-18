# 2020 CIEN 중급반 Unity3D 스터디

---

## 대상
 - 간단하게 프로그래밍을 할 수 있는 분들
    - 변수(int, float, double), 조건문(if), 반복문(while, for), 함수(메서드)를 이해하고 있다
 
 > 프로그래밍을 처음하는 분들은 힘들 수도 있습니다

## 목표
 - 유니티의 기본적인 조작을 할 수 있다
 - 유니티에서 `C#`을 사용해서 스크립트를 만들고 사용할 수 있다
 - 유니티 물리엔진을 이해하고 사용할 수 있다
    - 강체(Rigidbody): Velocity, Force, Mass, ... 
    - 충돌: Collision, Collider
 - 기초적인 UI를 만들 수 있다
    - 버튼 클릭
    - 씬 이동
    - HP바
    - ...
 - 게임의 데이터를 저장하고 불러올 수 있다
 - 유니티를 하면서 발생하는 오류들을 해결할 수 있다
    - 구글링, Stackoverflow, Manual, ... 검색 많이 해보기

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

### 일정 [`PDF`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/%EC%8A%A4%ED%84%B0%EB%94%94%20%EA%B3%84%ED%9A%8D.pdf) [`PPT`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/%EC%8A%A4%ED%84%B0%EB%94%94%20%EA%B3%84%ED%9A%8D.pptx)

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

> 숙제: 책상 만들기

- Material을 사용해보자

---

### 2주차. 유니티 스크립트
#### 2주차 스터디 자료: [`PPT`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/2.%20%EC%9C%A0%EB%8B%88%ED%8B%B0%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8.pptx) [`PDF`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/2.%20%EC%9C%A0%EB%8B%88%ED%8B%B0%20%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8.pdf)
 - 스크립트 개념
    - Start()
    - Update()
    - 이벤트 함수들의 실행 순서
    - Quiz. Class vs Instance
    - public인 변수들
    - Debug.Log()
 - 입력 처리
    - Input.GetKey(키코드)
        - Key, KeyDown, KeyUp
    - Input.GetMouseButton(0) // 0: 좌클릭, 1: 우클릭, 2: 중간(휠) 클릭
    - 입력 받아서 플레이어 움직이기
 - Vector3
     - 내적(dot)/외적(cross)
     - 사칙연산
 - struct 주의점
     - Quiz. struct vs class, 복사할 때 value type과 reference type의 동작 방식 
     - `transform.position.x = 2.3f;`가 사실은 `transform.GetPosition().x = 2.3f;`였다! 그래서 미리 컴파일러가 막아준다
 - Translate - self vs global
 - 처음보는 함수 ➡ [유니티 매뉴얼](https://docs.unity3d.com/kr/current/Manual/index.html)
 - Frame과 deltaTime
    - Framerate Independent하게 만들자!
    - `Update() { "오른쪽으로 한칸 움직여라" }`는 컴퓨터 성능과 비례한다
    - 모든 물체를 시간과 비례하도록 움직이게 해야한다
 - 물체의 이동과 회전
 - 에셋스토어
 
> 숙제: Flappy Bird의 새의 점프 구현하기

- 계속 점프가 가능해야 함
- 컴퓨터 성능과 무관해야 함
- `transform.position`만 이용해서 점프 구현

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

---

### 3주차. 물리엔진
#### 3주차 스터디 자료: [`PPT`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/3.%20%EC%9C%A0%EB%8B%88%ED%8B%B0%20%EB%AC%BC%EB%A6%AC%EC%97%94%EC%A7%84.pptx) [`PDF`](https://github.com/IamGroooooot/cien-unity-2020/raw/master/3.%20%EC%9C%A0%EB%8B%88%ED%8B%B0%20%EB%AC%BC%EB%A6%AC%EC%97%94%EC%A7%84.pdf)
 - 물리엔진이란?
    - 연산 타이밍?
    - `FixedUpdate()`
 - 강체(Rigidbody) 컴포넌트
    - 강체 - 물리에서의 정의와 유니티에서의 정의)
    - 물리엔진을 사용해보자
      - `rb = GetComponent<RigidBody>()`
      - `rb.velocity = new Vector3(0, 1, 0)`
      - `rb.AddForce(0, 500, 0)`
 - 충돌
    - Collider
    - Collision / Trigger
        - Enter, Stay, Exit
 
 > 숙제: 오늘 배운 `Collider`/`Trigger`/`Collision` 사용한 아무런 유니티 프로젝트 만들기
 
 > 제출: 위의 유니티 프로젝트를 [GitHub](https://github.com/)에 올린 후 링크 여기 톡방에 투척!
 
###### 제출 방법
 1. [GitHub](https://github.com/)에서 새로운 저장소(Repository)를 만든다.
   - 저장소의 이름은 자유롭게 설정
   - Description해도 되고 안해도 됨 (간략한 저장소 설명)
   - Public으로 설정
   - Initialize with README는 해도 되고 안해도 됨 (README는 프로젝트를 설명하는 파일임)
   - `.gitignore`를 unity로 설정
   - Add License해도 되고 안해도 됨 (내 저장소 저작권 설정하는 부분, MIT가 책임질 필요도 없고 무난함)
  
 2. 내 컴퓨터로 `Clone`한다
 3. 작업한 유니티 파일을 전부 `Clone`한 저장소로 옮긴다
 4. `Stage`에 모두 올린다
 5. 적절한 메시지와 함께 `Commit`하기
 6. `Push`한다!
 7. [GitHub](https://github.com/)에 들오가서 잘올라갔는지 확인한다
 8. 링크 톡방에 투척한다

---

### 4주차. 프리팹
 - 프리팹
 - 미사일 만들기
 - 미사일 생성하기
    - `Instantiate(복제대상)`
 - 적기(Enemy) 만들기
 - 게임오브젝트 찾기
    - Find / FindWithTag / FindObjectOfType
 - 코루틴을 위해 알아야 할 C# 문법
    - 람다식, IEnumerator, yield
 - 코루틴(Coroutine)이란?
    - 예제) Update Timer / Coroutine Timer 
 - 미사일 쏘는 적기 만들기
    - 플레이어가 적기의 미사일에 맞으면 "아야" 출력

> 숙제. https://github.com/CIEN-Club/workshop-guestbook의 README.md를 읽고 방명록 남기기

---

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

---

### 6주차. 유니티 UI
- UI 구성
    - 캔버스
    - 해상도
    - 앵커
- 텍스트
- 버튼
- 씬(Scene) 이동
    - GameOver 씬
- 점수창 만들기
    - 점수 매니저

---

### 7주차. 게임 데이터 관리
- PlayerPref
    - Enum
    - Save
    - Load
- 빌드하기
- 공유

---

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

---

수업 영상: [유튜브](https://www.youtube.com/playlist?list=PLl6IHQS9eTa0tv32BOR_jMvp1uatayAjs)
