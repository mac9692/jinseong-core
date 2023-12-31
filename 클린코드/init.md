# Clean Code - 로버트 C.마틴
## 클린코드
```
1. 코드가 존재하리라
코드는 더이상 문제가 아니라고, 모델이나 요구사항에 집중해야 한다고 생각하는 사람도 있으리라.
실제로도 코드의 종말이 코앞에 닥쳤다고 주장하는 사람이 없지 않다.
코드를 자동으로 생성하는 시대가 다가온다는 소리다. 그 때가 되면 영업직원이 명세에서 프로그램을 자동으로 생성하면 되니까 프로그래머는 필요가 없다.
헛소리! 앞으로 코드가 사라질 가망은 전혀 없다. 코드는 요구사항을 상세히 표현하는 수단이기 때문이다.
어느 수준에 이르면 상세한 표현은 불가피하다. 추상화도 불가능하다. 정확히 명시하는 수 밖에 없다.
기계가 실행할 정도로 상세하게 요구사항을 명시하는 작업, 바로 이것이 프로그래밍이고 이렇게 명시한 결과가 바로 코드다.
코드는 요구사항을 표현하는 언어이다. 그러므로 코드도 항상 존재하리라.

2. 나쁜코드
프로그래머라면 누구나 당연히 나쁜 코드로 고생한 경험이 있다.
그렇다면 묻겠다. 어째서 나쁜 코드를 짰는가? 급해서? 서두르느라? 아마 그랬으리라. 제대로 짤 시간이 없다고 생각해서,
코드를 다듬느라 시간을 보냈다가 상사한테 욕 먹을까봐, 지겨워서 빨리 끝내려고, 다른 업무가 너무 밀려 후딱 해치우고 밀린 업무로 넘어가려고
모두가 겪어온 상황이다.
우리 모두는 자신이 짠 쓰래기 코드를 쳐다보며 나중에 손보겠다고 생각한 경험이 있다.
우리 모두는 대충 짠 프로그램이 돌아간다는 사실에 안도감을 느끼며,
그래도 안 돌아가는 프로그램보다 돌아가는 쓰래기가 낫다고 스스로를 위로한 경험이 있다.
다시 돌아와서 나중에 처리하겠다고 다짐했었다. 물론 그 때 그 시절 우리는 르블랑의 법칙을 몰랐다.
"나중은 결코 오지 않는다."

3. 나쁜 코드로 치르는 대가
나쁜 코드가 쌓일수록 팀 생산성은 떨어진다. 그러다 결국 0에 근접한다.
생산성이 떨어지면 관리층은 나름ㄷ애로 복구를 시도한다. 어떻게? 생산성이 높아지리라는 희망을 품고 프로젝트에 인력을 추가로 투입한다.
하지만 새 인력은 시스템 설계를 충분히 이해하지 못한다. 설계 의도에 맞는 변경과 설계 의도에 반하는 변경을 구분하지 못한다.
게다가 새 인력과 팀은 생산성을 높여야 한다는 극심한 압력에 시달린다. 그래서 결국은 나쁜 코드를 더 많이 양산한다.
덕분에 생산성은 더더욱 떨어져 거의 0이 된다.

원대한 재설계의 꿈
 마침내 팀이 반기를 든다. 그들은 이처럼 혐오스러운 코드로 더 이상 일하지 못하겠다며 관리층에게 재설계를 요구한다.
관리층은 재설계에 자원을 쏟아 붓기 싫지만 생산성이 바닥이라는 사실을 부인할 도리가 없다. 결국은 팀이 요구하는 대로 원대한 재설계를 허락한다.
새로운 타이거 팀이 구성된다. 모두가 타이거 팀에 합류하고 싶어한다. 새로운 프로젝트니까. 처음부터 시작해서 진정으로 아름다운 작품을 창조할 기회니까.
하지만 가장 유능하고 똑똑한 사람들만 타이거 팀으로 차출된다. 나머지는 계속해서 현재 시스템을 유지 보수한다.
이제 두 팀이 경주를 시작한다. 타이거 팀은 기존 시스템 기능을 모두 제공하며, 추가되는 기능까지 제공하는 새 시스템을 내놓아야 한다.
새 시스템이 기존 시스템 기능을 100% 제공하지 않는 한 관리층은 기존 시스템을 대체하지 않을테니까.
때때로 경주는 아주 오랫동안 이어진다. 새 시스템이 기존 시스템을 따라잡을 즈음이면 초창기 타이거 팀원들은 모두 팀을 떠났고 새로운 팀원들이 새 시스템을 설계하자고 나선다.
왜? 현재 시스템이 너무 엉망이라서. 이야기의 교훈은 클린 코드를 만들려는 노력이 비용을 절감하는 방법일 뿐 아니라 전문가로서 살아남는 길이라는 사실을 인정하리라.

태도
좋은 코드가 어째서 순식간에 나쁜 코드로 전락할까? 우리는 온갖 이유를 들이댄다.
하지만 모든 것을 차치하고 잘못은 전적으로 프로그래머인 우리에게 있다. 우리가 전문가답지 못했기 때문이다.
비유를 하나 들겠다. 자신이 의사라 가정하자. 어느 환자가 시간이 너무 걸리니까 수술 전에 손을 씻지 말라고 요구한다.
확실히 환자는 상사다. 하지만 의사는 단호하게 거부한다. 왜? 질병과 감염의 위험은 의사가 환자보다 더 잘 아니까.
환자 말을 그대로 따르는 행동은 전문가답지 못하니까. 프로그래머도 마찬가지다.
나쁜 코드의 위험을 이해하지 못하는 관리자 말을 그대로 따르는 행동은 전문가답지 못하다.

클린 코드란
1. 나는 우아하고 효율적인 코드를 좋아한다. 논리가 간단해야 버그가 숨어들지 못한다.
의존성을 최대한 줄여야 유지보수가 쉬워진다. 클린 코드는 한 가지를 제대로 한다.
2. 클린 코드는 단순하고 직접적이다. 클린 코드는 잘 쓴 문장처럼 읽힌다.
클린 코드는 결코 설계자의 의도를 숨기지 않는다. 오히려 명쾌한 추상화와 단순한 제어문으로 가득하다.
3. 클린 코드는 작성자가 아닌 사람도 읽기 쉽고 고치기 쉽다.
단위 테스트 케이스와 수용 테스트 케이스가 존재한다.
4. 클린 코드가 보이는 특징은 많지만 그 중에서도 모두를 아우르는 특징이 하나 있다.
클린 코드는 언제나 누군가 주의 깊게 짰다는 느낌을 준다.
고치려고 살펴봐도 딱히 손 댈 곳이 없다. 작성자가 이미 모든 사항을 고려했으므로, 고칠 궁리를 하다보면 언제나 제자리로 돌아온다.
그리고는 누군가 남겨준 코드, 누군가 주의 깊게 짜놓은 작품에 감사를 느낀다.
5. 모든 테스트를 통과하라. 중복을 피하라. 한 기능만 수행하라. 제대로 표현하라. 작게 추상화하라. 이상이다.

우리는 저자다
Javadoc 에서 @author 필드는 저자를 소개한다. 우리는 저자다. 저자에게는 독자가 있다.
그리고 저자에게는 독자와 잘 소통할 책임도 있다.
다음에 코드를 짤 때는 자신이 저자라는 사실을, 우리의 노력을 보고 판단을 내릴 독자가 있다는 사실을 기억하기 바란다.
코드를 읽는 시간과 짜는 시간을 비교하면 비율로 10 : 1을 훌쩍 넘는다. 새 코드를 짜면서 우리는 끊임없이 기존 코드를 읽는다.
비율이 이렇게 높으므로 읽기 쉬운 코드가 매우 중요하다. 비록 읽기 쉬운 코드를 짜기가 쉽지는 않더라도 말이다.
하지만 기존 코드를 읽어야 새 코드를 짜므로 읽기 쉽게 만들면 사실은 짜기도 쉬워진다.
이 논리에서 빠져나갈 방법은 없다. 그러므로 급하다면, 서둘러 끝내려면, 쉽게 짜려면, 읽기 쉽게 만들면 된다.
빨리 가는 유일한 방법은 언제나 코드를 최대한 깨끗하게 유지하는 습관이다.

보이 스카우트 규칙
캠프장은 처음 왔을 때보다 더 깨끗하게 해놓고 떠나라.
많은 시간과 노력을 투자해 코드를 정리할 필요가 없다. 변수 이름 하나를 개선하고, 조금 긴 함수를 분할하고,
약간의 중복을 제거하고, 복잡한 If문 하나를 정리하면 충분하다.
시간이 지날수록 코드가 좋아지는 프로젝트에서 작업한다고 상상해보라. 전문가라면 너무도 당연하다.
지속적인 개선이야 말로 전문가 정신의 본질이 아니던가.
```

## 의미 있는 이름
```
소프트웨어에서 이름은 변수, 함수, 인수, 클래스와 패키지 및 원시 파일 등 어디에나 쓰인다.
따라서 이름을 잘 지으면 여러모로 편하다. 다음은 이름을 잘 짓는 몇 가지 간단한 규칙들이다.

1. 의도를 분명히 밝혀라
2. 그릇된 정보를 피하라
3. 의미 있게 구분하라
4. 발음하기 쉬운 이름을 사용하라
5. 검색하기 쉬운 이름을 사용하라
6. 인코딩을 피하라
7. 자신의 기억력을 자랑하지 마라
8. 클래스 이름
9. 메소드 이름
10. 기발한 이름은 피하라
11. 개념 하나에 단어 하나를 사용하라
12. 말장난을 하지 마라
13. 해법 영역에서 사용하는 이름을 사용하라
14. 문제 영역과 관련 있는 이름을 사용하라
15. 의미 있는 맥락을 추가하라
16. 불필요한 맥락을 없애라
```

## 함수
```
어떤 프로그램이든 가장 기본적인 단위가 함수다. 
다음은 함수를 잘 만드는 몇 가지 방법이다.

1. 작게 만들어라
2. 한 가지만 해라
3. 함수 당 추상화 수준은 하나로
4. Switch 문
5. 서술적인 이름을 사용하라
6. 함수 인수
7. 부수 효과를 일으키지 마라
8. 명령과 조회를 분리하라
9. 오류 코드보다 예외를 사용하라
10. 반복하지 마라
11. 구조적 프로그래밍
12. 함수를 어떻게 짜죠?
```
