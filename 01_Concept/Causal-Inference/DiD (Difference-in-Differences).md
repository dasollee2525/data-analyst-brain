---
tags: [concept, causal-inference]
axis: 분석방법론
created: 2026-05
---

## 한 줄 정의

처치 집단과 통제 집단의 변화량 차이로 인과 효과를 추정하는 방법. "처치 전후 차이"에서 "원래부터 있던 시간 트렌드"를 빼낸다.

## 언제 쓰는가 (전제 조건)

- 무작위 실험(A/B)이 불가능한 상황
- 처치 집단과 통제 집단이 존재
- **평행 트렌드 가정(Parallel Trends)**: 처치가 없었다면 두 집단이 같은 방향으로 움직였을 것
  - 검증: 처치 전 기간에 두 집단 트렌드가 평행한지 시각화 + 통계 검정

## 핵심 함정

1. **평행 트렌드 위반**: 처치 집단 선택이 이미 결과와 연관된 경우 (selection bias)
2. **spillover 효과**: 통제 집단이 처치의 영향을 간접적으로 받는 경우
3. **처치 시점 오염**: 처치와 동시에 다른 이벤트가 발생한 경우
4. **Staggered DiD**: 집단마다 처치 시점이 다를 때 단순 2x2 DiD는 편향 발생 → Callaway-Sant'Anna 등 사용

## 관련 개념

[[RDD (Regression Discontinuity Design)]] [[IV (Instrumental Variable)]] [[합성통제법 (Synthetic Control)]] [[A-B 테스트 기초]]

## 실제 케이스

*(경험 기록 후 추가)*

## 아직 모르는 것

- [ ] Staggered DiD에서 Callaway-Sant'Anna 방법론 직접 구현
- [ ] 평행 트렌드 검정: pre-trend test의 검정력 한계
