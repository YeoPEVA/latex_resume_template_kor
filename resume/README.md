# Resume Updater Guide

이 폴더는 이력서 원본(`.tex`)과 배포용 PDF(`.pdf`)를 별도로 보관하기 위한 유지보수용 폴더입니다.

## Folder Structure

```text
updater/
├── README.md
├── tex/
│   ├── resume_ko.tex
│   ├── resume_en.tex
│   ├── resume_dfir_ko.tex
│   ├── resume_dfir_en.tex
│   ├── resume_cert_ko.tex
│   └── resume_cert_en.tex
└── pdf/
    ├── resume_ko.pdf
    ├── resume_en.pdf
    ├── resume_dfir_ko.pdf
    ├── resume_dfir_en.pdf
    ├── resume_cert_ko.pdf
    └── resume_cert_en.pdf
```

## File Roles

- `tex/`: 향후 이력서 내용을 수정할 때 참고하거나 직접 수정할 LaTeX 원본입니다.
- `pdf/`: 현재 배포 또는 제출에 사용할 수 있는 PDF 산출물입니다.

## Resume Variants

- `resume_ko`: 기본 한국어 이력서
- `resume_en`: 기본 영문 이력서
- `resume_dfir_ko`: DFIR/디지털포렌식 직무용 한국어 이력서
- `resume_dfir_en`: DFIR/디지털포렌식 직무용 영문 이력서
- `resume_cert_ko`: CERT/침해대응/보안운영 직무용 한국어 이력서
- `resume_cert_en`: CERT/침해대응/보안운영 직무용 영문 이력서

## Recommended Update Flow

1. `tex/` 안의 수정 대상 `.tex` 파일을 편집합니다.
2. 같은 이름의 PDF를 새로 빌드합니다.
3. 빌드된 PDF를 `pdf/` 폴더에 덮어씁니다.
4. 필요하다면 최종 제출용 폴더인 `../yeopeva_resume/`에도 PDF를 복사합니다.

## Build Example

`updater/tex` 폴더에서 다음처럼 빌드할 수 있습니다.

```bash
cd /Users/yeopeva/Documents/codex_workspace/paper/latex_resume_template_kor/updater/tex
tectonic resume_ko.tex
```

빌드가 끝나면 생성된 PDF를 `updater/pdf`로 복사합니다.

```bash
cp resume_ko.pdf ../pdf/resume_ko.pdf
```

최종 제출용 폴더도 함께 갱신하려면 아래처럼 복사합니다.

```bash
cp resume_ko.pdf ../../yeopeva_resume/resume_ko.pdf
```

## Bulk Build Example

6개 이력서를 한 번에 빌드하려면 아래 명령을 사용할 수 있습니다.

```bash
cd /Users/yeopeva/Documents/codex_workspace/paper/latex_resume_template_kor/updater/tex
tectonic resume_ko.tex
tectonic resume_en.tex
tectonic resume_dfir_ko.tex
tectonic resume_dfir_en.tex
tectonic resume_cert_ko.tex
tectonic resume_cert_en.tex
```

빌드 후 PDF를 `updater/pdf`와 최종 제출용 폴더에 복사합니다.

```bash
cp resume_*.pdf ../pdf/
cp resume_*.pdf ../../yeopeva_resume/
```

## Content Maintenance Notes

- 연락처, 이메일, 웹사이트 링크는 6개 파일에 동일하게 반영하는 것이 좋습니다.
- 학력, 자격, 수상, 논문처럼 공통 이력에 해당하는 내용도 6개 파일에 모두 반영하는 것을 권장합니다.
- 요약(`Summary`/`요약`) 문단은 직무별로 다르게 유지합니다.
  - DFIR용: 포렌식, 침해사고 분석, 아티팩트 분석 중심
  - CERT용: 침해대응, 보안운영, 정책/관제 경험 중심
  - 기본용: 보안 분석과 자동화 관심을 균형 있게 표현
- 한국어와 영문 이력서는 의미가 대응되도록 유지하되, 문장을 직역하기보다 자연스러운 이력서 표현을 우선합니다.

## Current Source Relationship

이 `updater` 폴더는 유지보수용 복사본입니다.

기존 작업 원본은 다음 폴더에 남아 있습니다.

```text
../Curriculum_Vitae_Template/
```

최종 제출용 PDF 모음은 다음 폴더에 있습니다.

```text
../yeopeva_resume/
```

앞으로는 `updater/tex`를 기준 원본으로 삼고, 빌드 결과를 `updater/pdf`와 `../yeopeva_resume`에 함께 반영하면 관리가 가장 단순합니다.

## Quick Checklist Before Submission

- 이름, 이메일, 전화번호, GitHub, LinkedIn, 개인 사이트 링크 확인
- 한국어/영문 이력서의 날짜와 기관명 일치 여부 확인
- 자격증 유효기간 및 취득일 최신순 정렬 확인
- 수상 이력의 수상명, 수여기관, 수상일 확인
- 논문/학술대회 항목의 학회명, 일자, 페이지, 저자명 확인
- PDF가 최신 `.tex` 기준으로 재빌드되었는지 확인
- `updater/pdf`와 `../yeopeva_resume`의 PDF가 같은 최신본인지 확인
