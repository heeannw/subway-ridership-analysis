# 서울 지하철 승하차 데이터베이스 성능 개선

서울시 지하철 호선별·역별·시간대별 승하차 공공데이터를 SQLite에 적재하고, 인덱스 적용 전후의 조회 성능과 실행 계획을 비교한 트러블슈팅 프로젝트입니다.

## 주요 내용

- CP949 형식의 서울 지하철 승하차 CSV 로딩
- Pandas DataFrame을 SQLite 테이블로 변환
- `EXPLAIN QUERY PLAN`을 이용한 Full Table Scan과 Index Scan 비교
- 호선명·지하철역 복합 인덱스 적용
- 반복 조회를 통한 평균 응답 시간과 개선율 측정

## 저장소 구성

- `subway_troubleshooting.ipynb`: 데이터 적재와 인덱스 성능 실험
- `data/서울시 지하철 호선별 역별 시간대별 승하차 인원 정보.csv`: 분석에 사용한 78,630행 공공데이터

## 실행 방법

```bash
pip install -r requirements.txt
jupyter notebook subway_troubleshooting.ipynb
```

노트북은 Google Colab 기준 경로를 사용합니다. 로컬에서 실행할 때는 CSV 경로를 `data/` 폴더에 맞게 수정하세요. CSV 인코딩은 CP949입니다.

