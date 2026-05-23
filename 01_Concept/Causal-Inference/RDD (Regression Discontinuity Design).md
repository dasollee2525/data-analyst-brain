---
tags: [concept, causal-inference]
axis: 분석방법론
created: 2026-05
---

## 한 줄 정의

특정 임계값(cutoff)을 기준으로 처치 여부가 결정되는 상황에서, 그 경계 근처의 사람들을 비교해 인과 효과를 추정하는 방법.

## 언제 쓰는가 (전제 조건)

- 처치 배정이 **점수/임계값** 기준으로 이루어진 경우
  - 예: 신용점수 700 이상 → 대출 승인 / 이하 → 거절
  - 예: 앱 사용 N일 이상 → 리텐션 캠페인 대상
  - 예: 구매 금액 X만원 이상 → VIP 등급 부여
- running variable(점수)이 연속적이고, 사람들이 임계값을 **정확히 조작할 수 없는** 경우
- 임계값 근처에서 처치/비처치 집단이 사실상 동질적이라는 가정이 성립할 때

**Sharp RDD vs Fuzzy RDD**
- Sharp: 임계값 기준으로 처치 여부가 100% 결정 (가장 깔끔)
- Fuzzy: 임계값이 처치 확률을 높이지만 100%는 아님 → IV와 결합 필요

## 핵심 함정

1. **Sorting/Manipulation**: 사람들이 임계값 근처에서 점수를 조작할 수 있다면 가정 위반
   - 검증: McCrary density test — 임계값 주변에서 running variable 분포가 불연속적인지 확인
2. **Bandwidth 선택**: 임계값에서 얼마나 넓은 범위를 쓸지에 따라 결과가 달라짐
   - 너무 넓으면: 동질성 가정 위반 / 너무 좁으면: 샘플 부족
   - Optimal bandwidth 선택 알고리즘(Imbens-Kalyanaraman) 사용 권장
3. **Local 효과**: RDD는 임계값 근처에서의 효과(LATE)만 추정 — 전체 모집단으로 일반화 불가
4. **다른 불연속성 없어야 함**: 임계값에서 결과 외 다른 변수들도 동시에 점프하면 안 됨

## 관련 개념

[[DiD (Difference-in-Differences)]] [[IV (Instrumental Variable)]] [[합성통제법 (Synthetic Control)]] [[Situation-실험없이-인과추론이-필요할-때]]

## 실제 케이스

*(경험 기록 후 추가)*

## 아직 모르는 것

- [ ] McCrary density test 직접 구현 (Python/R)
- [ ] Fuzzy RDD에서 IV 결합 방법 실제 적용
- [ ] Bandwidth sensitivity analysis 시각화
