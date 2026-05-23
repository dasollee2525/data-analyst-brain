---
tags: [concept, causal-inference]
axis: 분석방법론
created: 2026-05
---

## 한 줄 정의

처치 변수에 영향을 주지만 결과에는 처치를 통해서만 영향을 주는 제3의 변수(도구변수)를 이용해 인과 효과를 추정하는 방법.

## 언제 쓰는가 (전제 조건)

- 처치 변수와 결과 변수 사이에 **관측되지 않은 교란변수(omitted variable)**가 있는 경우
- 처치 자체를 무작위 배정할 수 없고, DiD/RDD도 적용하기 어려울 때
- 유효한 도구변수를 찾을 수 있을 때

**도구변수의 3가지 조건**
1. **관련성 (Relevance)**: Z가 처치 D에 영향을 줌 (약한 도구변수 문제 → F-statistic > 10 확인)
2. **배제 제약 (Exclusion Restriction)**: Z가 결과 Y에 미치는 영향은 오직 D를 통해서만 (직접 효과 없음) — 검증 불가, 이론으로 정당화해야 함
3. **외생성 (Exogeneity)**: Z가 교란변수와 무관

**고전적 예시**
- 베트남 징병 추첨 번호 → 군복무 여부 → 임금 (Angrist 1990)
- 출생 분기 → 교육 연수 → 임금 (Angrist & Krueger 1991)
- 거리 → 대학 진학 → 임금

## 핵심 함정

1. **배제 제약 위반**: 가장 치명적, 검증이 불가능해서 이론적으로만 정당화 — 항상 비판받는 지점
2. **약한 도구변수 (Weak IV)**: Z와 D의 상관관계가 약하면 추정량이 편향 + 분산 폭증
   - 진단: 1단계 회귀의 F-statistic < 10이면 약한 도구변수 의심
3. **Local Average Treatment Effect (LATE)**: IV는 도구변수에 의해 처치가 바뀐 사람들(compliers)에 대한 효과만 추정 → 전체 모집단으로 일반화 불가
4. **좋은 도구변수 찾기 자체가 어려움**: 실무에서 IV를 제대로 쓰기 가장 어려운 이유

## 관련 개념

[[DiD (Difference-in-Differences)]] [[RDD (Regression Discontinuity Design)]] [[합성통제법 (Synthetic Control)]] [[Situation-실험없이-인과추론이-필요할-때]]

## 실제 케이스

*(경험 기록 후 추가)*

## 아직 모르는 것

- [ ] 2SLS (Two-Stage Least Squares) 직접 구현
- [ ] 배제 제약 정당화를 위한 이론적 논증 작성 연습
- [ ] 약한 도구변수 robust 추정법 (Anderson-Rubin test)
