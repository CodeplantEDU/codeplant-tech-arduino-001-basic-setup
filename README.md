# Arduino UNO R3 · IDE부터 첫 실행까지

CODEPLANT TECH 01 · 기본 세팅 (파랑 배경). Windows 10 이상, 64비트 PC와 Arduino IDE 2 기준입니다.

## 준비와 설치

Arduino UNO R3, 데이터 전송이 되는 USB-B 케이블, PC가 필요합니다. PC 쪽 단자는 USB-A 또는 PC에 맞는 단자를 쓰세요. 센서와 점퍼선은 필요하지 않습니다.

1. [Arduino 공식 다운로드](https://www.arduino.cc/en/software)에서 Arduino IDE 2의 Windows 64비트 설치 파일을 받습니다. 설치 후 실행합니다.
2. PC와 UNO의 USB-B 단자를 연결합니다. 이번 실습에서는 USB가 전원도 공급하므로 외부 전원은 추가하지 않습니다.
3. IDE에서 Arduino AVR Boards 패키지가 없으면 Boards Manager에서 설치합니다. 보드는 Arduino Uno를 선택합니다. UNO R4와 다른 보드입니다.
4. Tools > Port에서 연결한 UNO의 실제 COM 포트를 선택합니다. COM 번호는 PC마다 다릅니다. 보드 선택과 포트 선택은 각각 확인하세요.

| 확인할 것 | 설정 |
| --- | --- |
| 보드 패키지 | Arduino AVR Boards |
| 보드 | Arduino Uno (UNO R3), arduino:avr:uno |
| 포트 | 연결한 보드의 실제 COM 포트 |
| 시리얼 모니터 | 9600 baud |

## 첫 업로드

이 저장소의 sketch.ino를 내려받아 Arduino IDE에서 엽니다. IDE가 파일명과 같은 폴더 생성을 요청하면 허용합니다. Verify(체크 표시)로 컴파일한 뒤 Upload(오른쪽 화살표)를 누릅니다. 완료 메시지를 확인한 뒤 Serial Monitor(시리얼 모니터)를 열고 9600 baud로 맞춥니다.

보드의 L LED가 약 1초 켜지고 1초 꺼집니다. 시리얼 모니터에는 UNO READY가 약 2초마다 한 줄씩 나옵니다. 9600은 Serial.begin(9600)과 일치해야 합니다. LED_BUILTIN은 UNO R3의 내장 L LED를 가리킵니다. 외부 LED나 저항을 추가할 필요가 없습니다.

setup()은 시작할 때 한 번 실행하여 LED 출력과 통신을 설정합니다. loop()는 LED 켜기 → 문장 전송 → 1초 대기 → LED 끄기 → 1초 대기를 반복합니다. 연결 그림은 USB 연결 개념도입니다. diagram.json은 내장 LED 예제용 UNO만 배치했으며 USB를 GPIO 배선으로 표시하지 않습니다.

## 막혔을 때

- 포트가 안 보이면 데이터 케이블인지 확인하고 다른 USB 포트에 연결합니다. 연결 전후 목록에서 새로 나타난 포트를 찾습니다.
- Unknown으로 나오면 보드와 포트를 직접 선택합니다. 호환 보드의 USB 드라이버는 해당 보드 제조사 안내를 확인합니다.
- 업로드 오류는 보드·포트 설정과 케이블부터 확인하고 다른 프로그램의 시리얼 연결을 닫습니다.
- 문자가 깨지면 시리얼 모니터 속도를 9600으로 맞춥니다. Serial Monitor와 업로드 로그는 다른 화면입니다.

## 검증 범위

공식 문서와 보드·포트·실행 순서, 카드에 표시한 코드와 전체 코드의 대응을 검수했습니다. 실제 IDE 설치, UNO 업로드, 펌웨어 컴파일과 하드웨어 실행은 수행하지 않았습니다. 예상 LED·시리얼 결과를 실제 수업 보드에서 확인하세요.

## 사진과 출처

- UNO R3 사진: [SparkFun / Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Arduino_Uno_-_R3.jpg), [CC BY 2.0](https://creativecommons.org/licenses/by/2.0/). 원본 비율로 표시했습니다.
- IDE 2 화면: Arduino Documentation, Karl Söderby, [Using the Serial Monitor tool](https://docs.arduino.cc/software/ide-v2/tutorials/ide-v2-serial-monitor/), [원본 이미지](https://raw.githubusercontent.com/arduino/docs-content/main/content/software/ide-v2/tutorials/ide-v2-serial-monitor/assets/serial-monitor-new-editor.png). 공식 문서의 참고 화면이며 이 예제를 PC에서 실행한 캡처가 아닙니다. 크기만 조정했습니다. [문서 라이선스](https://github.com/arduino/docs-content/blob/main/LICENSE.md): [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). 이 이미지와 이를 포함한 카드 01은 CC BY-SA 4.0으로 제공합니다. 상표·공식 로고의 권리는 각 소유자에게 있습니다.
- [Arduino IDE 2 설치](https://docs.arduino.cc/software/ide-v2/tutorials/getting-started/ide-v2-downloading-and-installing/)
- [보드와 포트 선택](https://support.arduino.cc/hc/en-us/articles/4406856349970-Select-board-and-port-in-Arduino-IDE)
- [검증과 업로드](https://docs.arduino.cc/software/ide-v2/tutorials/getting-started/ide-v2-uploading-a-sketch/)
- 코드플랜트 시리즈: https://www.youtube.com/@codeplant2024

자료 확인: 2026-10-05. 다음 편은 신호처리입니다.
