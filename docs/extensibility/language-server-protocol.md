---
title: "언어 서버 프로토콜 개요 | Microsoft Docs"
ms.custom: 
ms.date: 11/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a7d93c2-31ea-4bae-8b29-6988a567ddf2
caps.latest.revision: "1"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 79022af292161d30440a01749ecc929ce7f3b511
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="language-server-protocol"></a>언어 서버 프로토콜

## <a name="what-is-the-language-server-protocol"></a>언어 서버 프로토콜 무엇입니까?

편집 기능을 지 원하는 풍부한 같은 소스 코드 자동 완성 또는 **정의로 이동** 편집기 또는 IDE에서 프로그래밍 언어는 일반적으로 매우 까다롭고 시간이 많이 소모 합니다. 일반적으로 도메인 모델 (스캐너, 한 파서, 형식 검사, 작성기를 등) 편집기 또는 IDE의 프로그래밍 언어로 작성 해야 합니다. 예를 들어 자체 Eclipse IDE Java로 작성 된 이후 Eclipse IDE의 C/c + +에 대 한 지원을 제공 하는 c d T Eclipse 플러그 인을 Java에 기록 됩니다. 이 방법에서는 다음 Visual Studio에 대 한 C# TypeScript for Visual Studio 코드에서에서 C/c + + 도메인 모델 및 별도 도메인 모델 구현 의미 합니다.

도메인 특정 언어 관련 모델을 만드는 개발 도구에는 기존 언어별 라이브러리 다시 사용할 수 있습니다 하는 경우에 훨씬 더 쉽게 됩니다. 그러나 이러한 라이브러리는 일반적으로 프로그래밍 언어 (예를 들어 좋은 C/c + + 도메인 모델 C/c + +에서 구현 되는) 자체에서 구현 됩니다. C/c + + 라이브러리 TypeScript로 작성 된 편집기 통합 가능 하지만 않고 기술적으로입니다.

### <a name="language-servers"></a>서버 언어

다른 방법은 자체 프로세스에서 라이브러리를 실행 하 고 선언 함 프로세스 간 통신을 사용할 것입니다. 송수신할 메시지 프로토콜을 형성 합니다. 언어 서버 프로토콜 LSP ()는 개발 도구와 언어 서버 프로세스 간에 교환 되는 메시지를 표준화 제품입니다. 언어 서버나 악마 사용 하지 않는 새롭거나 novel 좋습니다. Emacs 작업에 대해 의미 체계 자동 완성 기능 지원을 제공 하기 위해 약간의 시간이이 및 편집기 같은 Vim 합니다. LSP의 목적은 이러한 종류의 통합을 단순화 하 고 다양 한 도구를 언어 기능을 노출 하는 데 유용한 프레임 워크를 제공 하는 것 이었습니다.

일반 프로토콜 언어의 도메인 모델의 기존 구현이 다시 사용 하 여 간단 하 게 사용 하는 개발 도구에 대 한 프로그래밍 언어 기능 통합 수 있습니다. PHP, Python 또는 Java 언어 서버 백 엔드를 작성할 수 및 LSP 다양 한 도구에 쉽게 통합할 수 있게 합니다. 프로토콜 도구 갖는 기본 도메인 모델에만 완전히 이해 하지 않고도 다양 한 언어 서비스를 제공할 수 있도록 추상화 한 일반적인 수준에서 작동 합니다.

## <a name="how-work-on-the-lsp-started"></a>작동 방법 시작 LSP에

LSP가 발전 하 고 시간이 지남에 따라 되며 오늘 버전 3.0에 있습니다. 언어 서버 개념을 받았음을 OmniSharp 하 여 C#에 대 한 다양 한 편집 기능을 제공 하기 시작 합니다. 처음에 OmniSharp JSON 페이로드를 사용한 HTTP 프로토콜을 사용 하 고 포함 하 여 여러 명의 편집기에 통합 되었으며 [Visual Studio Code](https://code.visualstudio.com)합니다.

같은 시간대 Microsoft TypeScript Emacs 및 Sublime 텍스트와 같은 편집기에서 지 원하는 아이디어는 TypeScript 언어 서버에서 작업을 시작 합니다. 이 구현에서 편집기 stdin/stdout TypeScript 서버 프로세스를 통해 통신 하 고 V8 디버거 프로토콜와 같은 형식의 JSON 페이로드를 사용 하 여 요청 및 응답에 대 한 합니다. TypeScript 서버 TypeScript 다양 한 기능의 편집에 대 한 TypeScript Sublime 플러그 인 및 VS Code에 통합 되어 있습니다.

되 고 나면 두 명의 서로 다른 언어의 통합된 서버에서 VS Code 팀 탐색을 시작한 공용 언어 서버 프로토콜 편집기 및 Ide. 일반 프로토콜에는 여러 Ide에서 사용 될 수 있는 단일 언어 서버를 만들려면 언어 공급자를 수 있습니다. 언어 서버 소비자 프로토콜의 클라이언트 쪽을 한 번 구현 하는 있습니다. 이 언어 공급자 및 언어 소비자 모두에 대 한 win win 상황에서 발생합니다.

더 많은 일반 및 언어 독립적 된 TypeScript 서버에서 사용 되는 언어 프로토콜을 시작 합니다. 프로토콜 영감 VS Code 언어 API를 사용 하 여 많은 언어 기능이 포함 되었습니다. 프로토콜 자체는 여러 프로그래밍 언어에 대 한 해당 간단 명료 하 게 지원 라이브러리로 인 한 원격 호출에 대 한 JSON RPC로 지원 됩니다.

VS Code 팀 dogfooded 여러 linter 언어 서버를 구현 하 여 프로토콜입니다. Linter 언어 서버 보풀 (검색) 파일에 대 한 요청에 응답 하 고 검색 된 경고 및 오류 집합을 반환 합니다. 이 목표가 였습니다 보풀 파일 것 많은 linting 요청 편집기 세션 중는 문서에 사용자 편집 내용을으로 합니다. 이 기를 서버와 새 linting 프로세스 하지 않은 각 사용자 편집에 대 한 시작 해야 할 수 있도록 실행을 유지 하는 것입니다. VS Code를 포함 하 여 여러 linter 서버 구현 된 ESLint 및 TSLint 확장 합니다. 이러한 두 linter 서버가 모두 TypeScript/javascript에서 구현 및 Node.js에서 실행 합니다. 프로토콜의 클라이언트 및 서버 일부를 구현 하는 라이브러리 공유.

## <a name="how-the-lsp-works"></a>LSP 작동 방식

자체 프로세스에서 실행 되는 언어 서버 및 Visual Studio 또는 VS Code 같은 도구 언어 프로토콜을 사용 하 여 JSON RPC를 통해 서버와 통신 합니다. 전용된 프로세스에서 작동 하는 언어 서버의 또 다른 이점은 단일 프로세스 모델에 관련 된 성능 문제 방지 됩니다. 실제 전송 채널 수 stdio, 소켓, 명명 된 파이프 또는 노드 ipc 클라이언트와 서버 모두 Node.js에서 기록 하는 경우.

다음은 루틴 중 도구 및 언어 서버 간의 통신 하는 방법에 대 한 예제 편집 세션:

![lsp 흐름 다이어그램](media/lsp-flow-diagram.png)

* **사용자가 도구 (문서 라고 함) 파일을 열고**: 도구 언어 서버 문서가 열려 있는지 알립니다 (' textDocument/didOpen '). 이제 문서 내용에 대 한 참이 파일 시스템에 더 이상 되지만 메모리에 도구를 통해 유지 합니다.

* **사용자가 편집**: 도구 문서 변경 (' textDocument/didChange ')에 대 한 서버를에 알립니다. 고 프로그램의 의미 체계 정보가 언어 서버에 의해 업데이트 됩니다. 이런 경우, 언어 서버는이 정보를 분석 하 고 검색 된 오류 및 경고 (' textDocument/publishDiagnostics ')를 사용 하 여 도구를에 알립니다.

* **편집기에서 기호 "정의로 이동"를 실행 하는 사용자**: 두 개의 매개 변수가 함께 ' textDocument/정의 ' 요청을 전송 하는 도구: (1) 문서 URI 및 (2) 서버에 요청 정의로 이동 시작 된 위치에서 텍스트 위치 합니다. 서버 문서 URI 및 문서 내에서 기호 정의의 위치를 사용 하 여 응답 합니다.

* **사용자가 문서 (파일)**: 문서가 더 이상 메모리에 현재 내용을 이제 최신 상태 파일 시스템에는 이제 언어 서버를 알리는 도구에서 ' textDocument/didClose ' 알림이 전달 됩니다.

이 예제는 프로토콜 "정의로 이동", "모든 참조 찾기"와 같은 편집기 기능 수준에서 언어 서버와 통신 하는 방법을 보여 줍니다. 프로토콜에 의해 사용 되는 데이터 유형은 편집기 또는 IDE '데이터 형식' 현재 열려 있는 텍스트 문서 등 커서의 위치입니다. 데이터 형식이 추상 구문 트리 및 컴파일러 기호 (예: 확인 된 형식, 네임 스페이스,...) 일반적으로 제공 하는 프로그래밍 언어 도메인 모델 수준에서 되지 않습니다. 프로토콜을 훨씬 간단해 집니다.

이제 더 자세하게에서 ' textDocument/정의 ' 요청에 살펴보겠습니다. 다음은 클라이언트 도구와 c + + 문서에서 "정의로 이동" 요청에 대 한 언어 서버 간에 이동 하는 페이로드입니다.

다음은 요청입니다.

```json
{
    "jsonrpc": "2.0",
    "id" : 1,
    "method": "textDocument/definition",
    "params": {
        "textDocument": {
            "uri": "file:///p%3A/mseng/VSCode/Playgrounds/cpp/use.cpp"
        },
        "position": {
            "line": 3,
            "character": 12
        }
    }
}
```

다음은 응답입니다.

```json
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "uri": "file:///p%3A/mseng/VSCode/Playgrounds/cpp/provide.cpp",
        "range": {
            "start": {
                "line": 0,
                "character": 4
            },
            "end": {
                "line": 0,
                "character": 11
            }
        }
    }
}
```

에, 아니라 프로그래밍 언어 모델 수준에서 편집기의 수준에서 데이터 형식을 설명 하는 하나 언어 서버 프로토콜의 성공에 대 한 이유 중입니다. 텍스트 문서 URI를 표준화 하기 쉽고 인지 커서 위치 추상 구문 트리 및 컴파일러 기호 여러 프로그래밍 언어에서 표준화와 비교 합니다.

사용자가 서로 다른 언어를 사용할 때 VS Code는 일반적으로 각 프로그래밍 언어에 대 한 언어 서버를 시작 합니다. 다음 예제에서는 Java 및 SASS 파일에 사용자가 사용 되는 세션을 보여 줍니다.

![java 및 sass](media/lsp-java-and-sass.png)

### <a name="capabilities"></a>기능

모든 서버 프로토콜에 의해 정의 된 모든 기능을 지원할 수 있습니다. 따라서 클라이언트와 서버 '기능'을 통해가 지원 되는 기능 집합을 알립니다. 예를 들어 서버가 알립니다 ' textDocument/정의 ' 요청을 처리할 수 있지만 ' 작업 영역/기호 ' 요청을 처리 하지 수도 있습니다. 마찬가지로, '에 대 한 정보 저장'에 제공할 수는 클라이언트를 알릴 수 알림 서버를 자동으로 편집한 문서의 서식을 지정 하려면 텍스트 편집을 계산할 수 있도록 문서를 저장 하기 전에.

## <a name="integrating-a-language-server"></a>언어 서버 통합

특정 도구에 언어 서버의 실제 통합 언어 서버 프로토콜에 의해 정의 되지 않은 및 도구 구현자에 유지 됩니다. 일부 도구를 시작 하 고 모든 종류의 언어 서버와 통신할 수 있는 확장 하 여 언어 서버를 일반적으로 통합 합니다. 다른 사용자에 게 같이 VS Code 만들 언어 서버당 한 사용자 지정 확장 확장은 여전히 몇 가지 사용자 지정 언어 기능을 제공할 수 있도록 합니다.

를 간소화 하기 위해 언어 서버와 클라이언트의 구현이 있는 경우 라이브러리 또는 Sdk 클라이언트와 서버 부분에 대 한 이러한 라이브러리는 다른 언어에 대 한 제공 됩니다. 예를 들어, 한 [언어 클라이언트 npm 모듈](https://www.npmjs.com/package/vscode-languageclient) VS Code 확장 및 다른 언어 서버 통합을 보다 쉽게 [언어 서버 npm 모듈](https://www.npmjs.com/package/vscode-languageserver) Node.js를 사용 하는 언어 서버를 쓰려고 합니다. 이 현재 [목록](https://github.com/Microsoft/language-server-protocol/wiki/Protocol-Implementations) 지원 라이브러리입니다.

## <a name="using-the-language-server-protocol-in-visual-studio"></a>Visual Studio에서 언어 서버 프로토콜을 사용 하 여

* [서버 프로토콜 언어 확장 추가](adding-an-lsp-extension.md) -Visual Studio에는 언어 서버를 통합 하는 방법에 대 한 자세한 내용은 합니다.
