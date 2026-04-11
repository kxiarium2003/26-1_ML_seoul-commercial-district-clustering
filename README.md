# 26-1_ML_seoul-commercial-district-clustering
# 서울시 상권 군집화 분석

서울 열린데이터광장의 상권분석서비스 데이터를 활용해 서울시 상권을 군집화하고,  
실제 상권 구분(골목상권 / 발달상권 / 전통시장 / 관광특구)과 비교 분석한 프로젝트.

## 데이터

| 파일 | 출처 | 설명 |
|---|---|---|
| 서울시_상권분석서비스_추정매출-상권__2024년.csv | 서울 열린데이터광장 | 상권별 업종별 추정매출 (시간대·요일·성별·연령대) |
| 서울시_상권분석서비스_점포-상권__2024년.csv | 서울 열린데이터광장 | 상권별 업종별 점포수·개폐업률·프랜차이즈 현황 |
| 서울시_상권분석서비스_직장인구-상권_.csv | 서울 열린데이터광장 | 상권별 직장인구 (성별·연령대) |

> [상권분석서비스_추정매출-상권]([https://data.seoul.go.kr](https://data.seoul.go.kr/dataList/OA-15572/S/1/datasetView.do))
> [상권분석서비스_점포-상권]([https://data.seoul.go.kr](https://data.seoul.go.kr/dataList/OA-15577/S/1/datasetView.do))
> [상권분석서비스_직장인구-상권](https://data.seoul.go.kr/dataList/OA-15569/S/1/datasetView.do)

## 분석 개요

- **분석 단위**: 서울시 상권 1,581개 (2024년 4분기 기준)
- **Feature 수**: 30개 (매출 비율, 점포 현황, 직장인구 등)
- **Label (External Evaluation용)**: 상권_구분_코드_명 (4클래스)

## 방법론

| 알고리즘 | 주요 하이퍼파라미터 |
|---|---|
| K-Means | Elbow Method + Silhouette Score로 K 선택 |
| Hierarchical Clustering | Ward / Complete / Average linkage 비교 |
| DBSCAN | k-dist graph 기반 eps 탐색 |
| Affinity Propagation | damping 파라미터 탐색 |

차원 축소 시각화: **PCA** (2D / 3D), **t-SNE**


## 파일 구조

```
ML_HW2_seoul-commercial-district-clustering/
├── Data
├── clustering_hw.ipynb   
├── README.md
└── .gitignore
```

## 결과 요약
