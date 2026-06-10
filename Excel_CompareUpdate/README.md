# Excel_CompareUpdate

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![openpyxl](https://img.shields.io/badge/openpyxl-217346?style=flat-square)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)

> Excel comparison and update automation scripts built for office work.

<br>

사무보조 업무에서 반복적으로 수행하던 엑셀 비교 및 값 반영 작업을 줄이기 위해 만든 Python 스크립트 모음입니다.

비교 기준과 파일 구조에 따라 여러 버전으로 나누어 작성했으며,   
값이 같으면 **연두색**, 값이 다르면 값을 업데이트한 뒤 **주황색**으로 표시하도록 구성했습니다.

---

## Project Overview

이 프로젝트는 두 개의 엑셀 파일 또는 같은 파일 내 두 영역을 비교한 뒤,   
일치 여부를 색상으로 표시하고 필요한 경우 값을 자동 반영하기 위해 만든 업무 자동화 스크립트입니다.

폴더에는 기본 비교 버전, 소수점 및 문자열 정리까지 반영한 버전, 두 파일 비교 버전, 특정 키 값을 기준으로 매칭하는 버전이 포함되어 있습니다.

---

## Key Features

### Excel_CpUpdate1

* 같은 엑셀 파일 내 두 컬럼 구간을 비교
* `C~E ↔ F~H`, `M~O ↔ P~R` 구간을 대상으로 처리
* 값이 같으면 연두색 표시
* 값이 다르면 기준 값을 복사하고 주황색 표시
* 결과를 `updated_excel.xlsx`로 저장

### Excel_CpUpdate2

* 기본 비교 구조는 유지하면서 값 정리 로직 추가
* `None`, 공백, 특수문자 제거 후 비교
* 숫자는 `pandas.to_numeric`으로 변환 후 소수점 6자리까지 반올림하여 비교
* 결과를 `updated_excel2.xlsx`로 저장

### Excel_CpUpdate_2files

* 서로 다른 두 엑셀 파일을 비교
* 엑셀1의 `B14:B255` 값을 기준으로 엑셀2의 `A`열에서 같은 값을 검색
* 매칭된 행끼리 엑셀1 `H~S`와 엑셀2 `B~M`을 비교
* 값이 다르면 엑셀2 값을 엑셀1에 반영
* 결과를 `updated_원본파일명.xlsx` 형식으로 저장

### Excel_CpUpdate_Match

* 두 엑셀 파일에서 특정 키 값을 기준으로 행을 매칭
* 엑셀1의 특정 열 값과 엑셀2 `C`열 값을 비교해 대응 행 탐색
* 매칭된 행의 대상 셀 값을 비교 후 업데이트
* 결과를 `Updated_원본파일명.xlsx` 형식으로 저장

---

## Tech Stack

* **Language**: Python
* **Library**: openpyxl, pandas

---

## Project Structure

```text
Excel_CompareUpdate/
├── Excel_CpUpdate1.py
├── Excel_CpUpdate1.md
├── Excel_CpUpdate2.py
├── Excel_CpUpdate2.md
├── Excel_CpUpdate_2files.py
├── Excel_CpUpdate_2files.md
├── Excel_CpUpdate_Match.py
├── Excel_CpUpdate_Match.md
└── README.md
```

---

## Program Flow

### Same-file Compare Flow

1. 파일 경로와 시트명 지정
2. 비교할 두 컬럼 구간 선택
3. 셀 값을 비교
4. 같으면 연두색, 다르면 값 복사 후 주황색 표시
5. 새 파일로 저장

### Two-file Compare Flow

1. 두 엑셀 파일 열기
2. 기준 열 값을 사용해 대응 행 찾기
3. 지정된 컬럼 범위를 비교
4. 차이가 있으면 값 업데이트 및 색상 표시
5. 수정된 파일 저장

---

## Implementation Highlights

### Color-based Result Check

모든 스크립트에서 비교 결과를 바로 확인할 수 있도록   
같은 값은 연두색, 다른 값은 주황색으로 표시하도록 구현했습니다.

### Same-file Range Comparison

하나의 파일 안에서 두 영역을 직접 비교하고 업데이트할 수 있도록 구성했습니다.   
반복적으로 대조해야 하는 시트 작업을 줄이는 데 초점을 두었습니다.

### Cross-file Matching and Update

두 파일 간 비교가 필요한 경우를 위해,   
기준 키 값을 찾은 뒤 대응 행의 여러 컬럼 값을 한 번에 반영할 수 있도록 작성했습니다.

### Value Cleaning for Stable Comparison

숫자 형식, 공백, 특수문자 차이 때문에 동일한 값이 다르게 인식되는 문제를 줄이기 위해   
값 정리 및 소수점 처리 버전을 별도로 만들었습니다.

---

## What I Learned

* Python으로 엑셀 파일을 직접 읽고 수정하는 방법
* openpyxl을 활용해 셀 값과 서식을 함께 다루는 방법
* 같은 파일 비교와 두 파일 비교를 각각 다른 방식으로 구현하는 방법
* 업무 데이터에서 숫자 형식, 공백, 특수문자 차이를 고려해야 한다는 점
* 반복적인 엑셀 대조 작업을 스크립트로 자동화하는 방법

---

## Limitations

* 파일 경로와 시트명을 코드에서 직접 수정해야 합니다.
* 비교 범위와 기준 컬럼이 업무용 엑셀 구조에 맞춰 고정되어 있습니다.
* 예외 처리와 입력 검증은 최소한으로 구성되어 있습니다.
* 범용 도구보다는 특정 업무 양식에 맞춘 스크립트 형태입니다.

---

## Author

Yeeun Park

GitHub: [dPdms21](https://github.com/dPdms21)
