# PDF_BookMark

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyMuPDF](https://img.shields.io/badge/PyMuPDF-4B8BBE?style=flat-square)

> PDF bookmark automation scripts built for office work.

<br>

사무보조 업무에서 반복적으로 수행하던 PDF 책갈피 작업을 자동화하기 위해 만든 Python 스크립트입니다.   
기본 버전과 **시작 번호를 지정할 수 있는 버전**으로 구성했습니다.

---

## Project Overview

이 프로젝트는 PDF 문서에 책갈피를 수작업으로 추가하던 과정을 줄이기 위해 만든 Python 기반 자동화 스크립트입니다.

PyMuPDF를 사용해 PDF를 열고, 기존 책갈피를 제거한 뒤   
각 페이지에 맞는 책갈피를 자동으로 생성하여 새로운 PDF 파일로 저장하도록 구현했습니다.

---

## Key Features

### PDF_BookMark

* PDF의 모든 페이지에 대해 책갈피 자동 생성
* 책갈피 이름을 `1, 2, 3, ...` 형태의 페이지 번호로 설정
* 기존 책갈피(TOC) 제거 후 새 책갈피 적용
* 수정된 PDF를 새 파일로 저장

### PDF_BM_Start_Num

* 시작 번호를 직접 입력하여 책갈피 생성
* 입력한 번호를 기준으로 순차적인 책갈피 생성
* PDF 페이지 수만큼 책갈피 자동 추가
* 결과를 새 PDF 파일로 저장

---

## Tech Stack

* **Language**: Python
* **Library**: PyMuPDF (`fitz`)
* **Environment**: Local / Office Work Automation Script

---

## Project Structure

```text
PDF_BookMark/
├── PDF_BM_Start_Num.py
├── PDF_BM_Start_Num.md
├── PDF_BookMark.py
├── PDF_BookMark.md
└── README.md
```

---

## Program Flow

### PDF_BookMark Flow

1. 입력 PDF 경로 입력
2. 출력 PDF 경로 입력
3. 기존 책갈피 제거
4. 전체 페이지 기준 책갈피 생성
5. 새 PDF 파일로 저장

### PDF_BM_Start_Num Flow

1. 입력 PDF 경로 입력
2. 출력 PDF 경로 입력
3. 시작 번호 입력
4. 입력한 번호를 기준으로 책갈피 생성
5. 새 PDF 파일로 저장

---

## Implementation Highlights

### Automatic Bookmark Generation

PDF 전체 페이지를 순회하면서 각 페이지에 대응하는 책갈피를 자동 생성하도록 구현했습니다.

### TOC Reset

기존 책갈피가 있는 문서도 다시 정리할 수 있도록, 기존 TOC를 비운 뒤 새 책갈피를 적용하도록 구성했습니다.

### Start Number Customization

문서 특성에 따라 특정 번호부터 책갈피를 시작해야 하는 경우를 위해 시작 번호 입력 버전을 별도로 만들었습니다.

### Simple CLI Input

별도 UI 없이 파일 경로와 시작 번호만 입력하면 바로 실행할 수 있도록 단순한 CLI 형태로 작성했습니다.

---

## What I Learned

* Python으로 PDF 문서를 직접 다루는 방법
* PyMuPDF를 활용해 TOC(책갈피)를 생성하고 수정하는 방법
* 반복적인 사무 작업을 간단한 스크립트로 자동화하는 방법
* 기본 기능과 옵션 기능을 분리해 스크립트를 관리하는 방법

---

## Limitations

* 파일 경로를 직접 입력해야 하는 CLI 방식입니다.
* 예외 처리와 사용자 입력 검증은 최소한으로 구성되어 있습니다.
* 대량 파일 일괄 처리 기능은 포함되어 있지 않습니다.

---

## Author

Yeeun Park

GitHub: [DevLucia-21](https://github.com/DevLucia-21)
