# 학습 요약 (2025-08-29)

## 작업 내용
C언어로 BMP 이미지 처리 및 Verilog용 `.mem` 파일 생성.

## 주요 기능
1.  **그레이스케일 변환**
    -   **입력**: `brainct_001.bmp` (24비트 컬러)
    -   **출력**: `output_grayscale.bmp` (8비트 흑백)
    -   **로직**: 각 픽셀의 RGB 값을 휘도 공식(`Y = 0.299*R + 0.587*G + 0.114*B`)을 이용해 흑백 값으로 변환.

2.  **MEM 파일 생성**
    -   **출력**: `output_image.mem`
    -   **목적**: Verilog 시뮬레이션 메모리 초기화.
    -   **형식**: 흑백 픽셀 값을 16진수로 변환하여 한 줄에 하나씩 저장.
    ```c
    // 핵심 코드
    fprintf(memOutFile, "%02X\n", grayscaleData[i]);
    ```

## 관련 파일
-   **소스 코드**: `bmp_to_mem_converter.c`
-   **결과물**: `output_grayscale.bmp`, `output_image.mem`
