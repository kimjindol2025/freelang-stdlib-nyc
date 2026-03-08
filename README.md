# freelang-stdlib-nyc

FreeLang v2 stdlib — npm `nyc` 완전 대체

코드 커버리지 측정 및 리포트 생성

## 사용법

```freelang
import nyc from "stdlib/nyc"

// 커버리지 수집 시작
nyc.start()

// 테스트 실행
runTests()

// 커버리지 수집 종료 및 리포트
var report = nyc.stop()
println("Lines: " + str(report.lines) + "%")

// 커버리지 임계값 검증
if nyc.checkCoverage({ lines: 80, functions: 90 }) {
  println("커버리지 기준 충족")
}

// 리포트 출력 (text, json, html)
nyc.report("text")
nyc.report("json")
nyc.report("html")  // /coverage/index.html 생성
```

## API

| 함수 | 설명 |
|------|------|
| `start()` | 커버리지 수집 시작 |
| `stop()` | 수집 종료 및 리포트 |
| `reset()` | 초기화 |
| `checkCoverage(thresholds)` | 임계값 검증 |
| `report(format)` | 리포트 출력 |
| `addFile(name, lines)` | 파일 추가 |
| `markLineExecuted(file, line)` | 라인 실행 마크 |
| `markFunctionExecuted(file)` | 함수 실행 마크 |
| `getLastReport()` | 마지막 리포트 |

## CoverageReport

- `lines: float` — 라인 커버리지 %
- `functions: float` — 함수 커버리지 %
- `branches: float` — 분기 커버리지 %
- `statements: float` — 명령문 커버리지 %
- `uncoveredLines: map` — 파일 → [라인번호]
- `files: map` — 파일별 상세 정보

## 라이선스

FreeLang Project
