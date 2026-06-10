# Office Work Automation

[2024] Office Work

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyMuPDF](https://img.shields.io/badge/PyMuPDF-4B8BBE?style=flat-square)
![openpyxl](https://img.shields.io/badge/openpyxl-217346?style=flat-square)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)

> Office automation scripts built to reduce repetitive document and spreadsheet tasks.

<br>

사무보조 업무 중 반복적으로 수행하던 문서 및 엑셀 작업을 줄이기 위해 만든 Python 자동화 스크립트 저장소입니다.

이 저장소는 **PDF 책갈피 생성**과 **엑셀 비교 및 업데이트 자동화** 스크립트로 구성되어 있습니다.

---

## Projects

### PDF_BookMark

PDF 문서의 각 페이지에 책갈피를 자동으로 생성하는 스크립트입니다.

#### Main Features

* PDF 전체 페이지 기준 책갈피 생성
* 기존 책갈피 제거 후 새 TOC 적용
* 시작 번호 지정 가능

📁 [PDF_BookMark](PDF_BookMark/)

---

### Excel_CompareUpdate

엑셀 파일 또는 같은 파일 내 두 영역을 비교하고,   
필요한 경우 값을 업데이트한 뒤 색상으로 결과를 표시하는 스크립트 모음입니다.

#### Main Features

* 같은 파일 내 셀 비교 및 업데이트
* 두 파일 간 값 비교 및 반영
* 기준값을 이용한 행 매칭 비교
* 연두색 / 주황색 표시를 통한 결과 확인

📁 [Excel_CompareUpdate](Excel_CompareUpdate/)

---

## Tech Stack

* Python
* PyMuPDF
* openpyxl
* pandas

---

## Repository Structure

```text
Office-Work
├── Excel_CompareUpdate
├── PDF_BookMark
└── README.md
```

---

## Author

Yeeun Park

GitHub: [dPdms21](https://github.com/dPdms21)
