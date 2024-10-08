### [개념] 안녕 해시! | 자료구조·알고리즘

**배열의 한계:**
- 배열에서 값을 찾기 위해 위치를 명시해 값을 찾습니다.
- 모든 값을 찾기 위해 이런 방식으로 진행하기에는 무리가 있습니다.
- 예를 들어, 아이디와 비밀번호를 비교해야 하는 로그인 시스템을 생각해봅시다.

**아이디와 비밀번호 비교:**
- 아이디와 비밀번호를 쌍으로 묶어 저장하는 방법이 있습니다.
- 그러나 대소관계 비교가 어렵고, 특수문자가 포함되면 정리하기 힘듭니다.
- 정렬을 하지 않으면 로그인 시 모든 정보를 뒤져야 하는 단점이 있습니다.
- 사이트 규모가 커지면, 시간복잡도 O(logN)도 성능이 떨어질 수 있습니다.

**해시 함수의 도입:**
- 해시 함수는 임의의 데이터를 받아 고정된 길이의 특정 값으로 반환하는 함수입니다.
- 특정 값을 배열에 넣기 위해 해시 함수를 사용해 인덱스를 얻어 해당 인덱스에 값을 저장합니다.
- 이렇게 하면 삽입, 삭제, 검색이 모두 O(1)로 가능합니다.

**해시 함수의 한계:**
- 모든 타입에 대응하지 않습니다. 예를 들어 배열 같은 타입은 다루지 않습니다.
- 배열 내 값

### 해시 함수와 해시 테이블
- 해시 함수는 입력 값을 특정 범위의 정수로 변환하는 함수입니다.
- 변환된 정수 값을 인덱스로 사용하여 배열에 값을 저장합니다.
- 예시: f(x) = x % 10
  - 입력 값이 239, 6, 197, 638, 372일 때, 해시 함수의 반환 값은 각각 9, 6, 7, 8, 2가 됩니다.
  - 반환 값이 인덱스로 사용되어 배열에 값을 저장합니다.

### 해시 충돌
- 해시 충돌은 서로 다른 입력 값이 동일한 해시 값을 가질 때 발생합니다.
- 예시: 239, 9, 199, 368, 372의 해시 값이 각각 9, 9, 9, 8, 2일 때, 9 인덱스에서 충돌이 발생합니다.
- 해시 충돌이 발생하면 일반 배열로는 문제를 해결할 수 없습니다.

### 해시 충돌 해결 방법
- **연결 리스트 사용**: 충돌이 발생한 인덱스에 연결 리스트를 사용하여 값을 저장합니다.
  - 예시: 인덱스 9에 연결 리스트를 두어 239, 9, 199를 순서대로 저장합니다.
  - 탐색, 삽입, 삭제 시 연결 리스트를 순회하여 값을 찾습니다.
- 연결 리스트 사용 시 최악의 경우 시간 복잡도는 O(N)이 됩니다.

### 해시 함수 설정
- 해시 충돌을 최소화하기 위해 적절한 해시 함수를 설정하는 것이 중요합니다.
- 충돌이 거의 없다면, 해시 테이블을 통한 조회, 삽입, 삭제의 시간 복잡도는 O(1)입니다.

### 해시 테이블 크기
- 실제 데이터 양보다 몇 배 더 큰 배열을 사용하여 해시 테이블을 정의합니다.
- 일반적으로 최대 데이터의 3~4배 정도의 크기로 설정합니다.

### 요약
- 해시 충돌은 동일한 해시 값을 가지는 서로 다른 입력 값이 배열의 동일 인덱스에 저장될 때 발생합니다.
- 연결 리스트를 사용하여 충돌을 해결할 수 있으며, 적절한 해시 함수 설정과 충분한 해시 테이블 크기로 충돌을 최소화할 수 있습니다.
- 해시 테이블은 충돌이 없을 경우 O(1)의 시간 복잡도를 가집니다.

저작권자 © 브랜치앤바운드 코드트리 사이트의 모든 교육자료는 저작권법의 보호를 받습니다. 작성자의 동의 없는 무단 전재/복사/배포 등을 금지합니다.