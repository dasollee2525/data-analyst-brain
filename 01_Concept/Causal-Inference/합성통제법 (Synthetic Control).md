---
tags: [concept, causal-inference]
axis: 분석방법론
created: 2026-05
---

## 한 줄 정의

여러 통제 집단을 가중 합산해 "처치가 없었다면 어땠을까"를 나타내는 가상의 통제군을 합성하는 방법. 통제군이 하나뿐이거나 DiD의 평행 트렌드 가정이 성립하지 않을 때 쓴다.

## 언제 쓰는가 (전제 조건)

- **처치 집단이 1개** (또는 소수)인 경우 — DiD는 다수 처치 집단에 더 적합
- 처치 전 기간이 충분히 긺 (가중치 최적화에 필요)
- 비교 가능한 통제 집단(donor pool)이 여러 개 존재
- DiD의 평행 트렌드 가정이 시각적으로 성립하지 않는 경우

**고전적 예시**
- 캘리포니아 담배세 인상(1988)의 효과: 나머지 주들을 합성해 "담배세 없는 캘리포니아" 구성 (Abadie et al. 2010)

## 핵심 함정

1. **Donor pool 선택**: 처치 집단과 너무 다른 집단을 포함하면 합성이 잘못됨
   - 원칙: 처치 전 기간에 결과 변수 + 예측변수가 유사한 집단만 포함
2. **처치 전 fit이 나쁘면 신뢰 불가**: 합성 통제군이 처치 전 실제값을 잘 재현하지 못하면 처치 후 예측도 신뢰할 수 없음
3. **Placebo test 필수**: 각 통제 집단에 가상의 처치를 적용해 비슷한 효과가 나오는지 확인 — 안 나와야 진짜 효과
4. **샘플 작을수록 통계적 추론 어려움**: p-value 계산이 permutation 기반이라 donor pool이 작으면 검정력 약함
5. **외삽(extrapolation) 문제**: 가중치가 음수가 되거나 특정 집단에 과도하게 쏠리는 경우 결과 불안정

## 관련 개념

[[DiD (Difference-in-Differences)]] [[IV (Instrumental Variable)]] [[RDD (Regression Discontinuity Design)]] [[Situation-실험없이-인과추론이-필요할-때]]

## 실제 케이스

*(경험 기록 후 추가)*

## 아직 모르는 것

- [ ] Python `SyntheticControlMethods` 라이브러리 실제 사용
- [ ] Donor pool 선택 기준 정량화 방법
- [ ] Augmented Synthetic Control (Ben-Michael et al.) — 편향 보정 버전
