# Two-Stack Queue 시각화

두 개의 스택으로 큐(Queue)를 구현하는 자료구조 알고리즘을 인터랙티브하게 시각화한 HTML 데모입니다.

## 개념

큐(FIFO)를 스택(LIFO) 두 개로 구현합니다.

- **Stack 1 (inbox)** — `enqueue` 시 push
- **Stack 2 (outbox)** — `dequeue` 시 pop. outbox가 비어 있으면 inbox의 모든 원소를 옮긴 뒤 pop

```
enqueue(1) → s1: [1]
enqueue(2) → s1: [1, 2]
dequeue()  → s2가 비어 있으므로 s1 전체를 s2로 이동 → s2: [2, 1] → pop → 1 반환
dequeue()  → s2: [2] → pop → 2 반환
```

## 시간 복잡도

| 연산 | 복잡도 |
|------|--------|
| Enqueue | O(1) |
| Dequeue | O(1) amortized |
| 공간 | O(n) |

각 원소는 inbox → outbox 이동을 **최대 1번**만 수행하므로 dequeue의 amortized 비용은 O(1)입니다.

## 사용법

`two_stack_queue.html` 파일을 브라우저에서 열거나 Claude Code 프리뷰 패널에서 확인합니다.

| 버튼 | 동작 |
|------|------|
| Enqueue | 입력값을 Stack 1에 push |
| Dequeue | Stack 2에서 pop (비어 있으면 Stack 1 전체를 먼저 이동) |
| 초기화 | 모든 상태 초기화 |

## 파일 구조

```
two_stack_queue.html   # 스타일 + 마크업 + 로직 단일 파일
```
