# [리눅스] C Shell (csh) trap 사용법: 신호 처리 및 종료 시 동작 정의

## Overview
`trap` 명령은 C Shell에서 특정 신호를 수신했을 때 실행할 동작을 정의하는 데 사용됩니다. 이 명령을 사용하면 스크립트가 종료되거나 중단될 때 특정 작업을 수행할 수 있습니다.

## Usage
기본 구문은 다음과 같습니다:

```csh
trap [options] [arguments]
```

## Common Options
- `SIGINT`: 사용자 인터럽트 신호(일반적으로 Ctrl+C)를 처리합니다.
- `SIGTERM`: 종료 신호를 처리합니다.
- `EXIT`: 스크립트가 종료될 때 실행할 명령을 지정합니다.

## Common Examples
다음은 `trap` 명령의 몇 가지 실용적인 예입니다.

### 예제 1: Ctrl+C 신호 처리
사용자가 Ctrl+C를 눌렀을 때 메시지를 출력하도록 설정합니다.

```csh
trap 'echo "프로그램이 중단되었습니다."' SIGINT
```

### 예제 2: 스크립트 종료 시 클린업
스크립트가 종료될 때 특정 파일을 삭제합니다.

```csh
trap 'rm -f /tmp/tempfile' EXIT
```

### 예제 3: 종료 신호 처리
종료 신호를 수신했을 때 사용자에게 알림을 보냅니다.

```csh
trap 'echo "종료 신호를 수신했습니다."' SIGTERM
```

## Tips
- `trap` 명령은 스크립트의 안정성을 높이는 데 유용합니다. 예를 들어, 중요한 작업을 수행하는 스크립트에서 클린업 작업을 정의할 수 있습니다.
- 여러 신호를 동시에 처리할 수 있으므로, 필요에 따라 여러 `trap` 명령을 설정할 수 있습니다.
- `trap`을 사용하여 디버깅 정보를 출력하거나 로그 파일을 작성하는 것도 좋은 방법입니다.