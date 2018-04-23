---
title: JIT 최적화 및 디버깅 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], optimized code
- optimized code, debugging
ms.assetid: 19bfabf3-1a2e-49dc-8819-a813982e86fd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9a9b18ab38c7c19fa5208d34439bd3133099e8bc
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="jit-optimization-and-debugging"></a>JIT 최적화 및 디버깅
**최적화.NET에서 작동 하는 방법:** 코드를 디버깅 하려는 경우 더 쉽게 때 코드는 **하지** 최적화 합니다. 코드가 최적화 되 면 컴파일러와 런타임은 변경할 내보낸된 CPU 코드를 더 빨리 실행 하지만 원래 소스 코드에 직접 매핑을 않도록 때문입니다. 즉, 디버거를 자주 코드 단계별 실행 및 지역 변수의 값을 알 수 없는 중단점 예상 대로 작동 하지 않을 수 있습니다.

일반적으로 릴리스 빌드 구성 최적화 된 코드 만들고 디버그 빌드 구성 하지 않습니다. `Optimize` MSBuild 속성 코드를 최적화 컴파일러 지시 있는지 여부를 제어 합니다.

.NET 에코 시스템에서 코드 옵션이 소스에서 2 단계 프로세스의 CPU 지침: C# 컴파일러 MSIL을 호출 하는 중간 이진 형식으로 입력 하는 텍스트를 변환 하 고.dll 파일에이 작성 하는 먼저 합니다. 나중.NET 런타임 CPU 지침에 대 한이 MSIL을 변환합니다. 두 단계를 어느 정도 최적화할 수 있지만 보다 중요 한 최적화를 수행 하는.NET 런타임이 수행 하는 두 번째 단계입니다.

**'(관리 전용) 모듈을 로드할 때 JIT 최적화' 옵션:** 디버거가 대상 프로세스 내에서 사용 되는 최적화로 컴파일한 DLL을 로드할 때의 동작을 제어 하는 옵션을 노출 합니다. 이 옵션을 선택 하지 않으면 (기본 상태),.NET 런타임 CPU 코드를 MSIL 코드 컴파일되면 벗어나 최적화 기능을 사용 합니다. 옵션을 선택 하는 경우 디버거에서 최적화가 해제 될 요청 합니다.

**(관리 전용) 모듈을 로드할 때 JIT 최적화** 옵션에서 확인할 수 있습니다는 **일반** 페이지는 **디버깅** 의 노드는 **옵션** 대화 상자.

**이 옵션을 선택 해야 경우 있습니다:** nuget 패키지와 같은 다른 원본에서 Dll을 다운로드 하 고이 DLL의 코드를 디버깅 하려는 경우이 옵션을 선택 합니다. 이 작업을 위해도이 DLL에 대 한 기호 (.pdb) 파일을 찾아야 합니다.

로컬에서 작성 하는 코드를 디버깅만 하려는 경우에 되도록 하려면이 옵션 선택 되지 않은 경우에 따라이 옵션을 사용 하면 훨씬 느려집니다 디버깅 하는 대로 가장 좋습니다. 속도 저하이 대 한 두 가지 이유가 있습니다.

* 최적화 된 코드를 더 빠르게 실행 됩니다. 많은 코드에 대 한 최적화 기능을 해제 하는 경우 성능에 영향을 추가할 수 있습니다.
* 사용 하도록 설정 하는 내 코드만 있으면 디버거가 시도 및 최적화 된 Dll에 대 한 기호를 로드 하더라도 됩니다. 기호 찾기 시간이 오래 걸릴 수 있습니다.

**이 옵션의 제한 사항:** 다음 두 가지 경우가이 옵션은 여기서 **하지** 작동 합니다.

1. 이미 실행 중인 프로세스에 디버거를 연결 되는 있는 경우에이 옵션에 디버거가 연결 된 시간에 이미 로드 된 모듈에 영향을 주지 갖습니다.
2. 이 옵션은 된 Dll에 아무런 영향 미리 (사항 하루가 지난)를 네이티브 코드로 컴파일됩니다. 그러나 환경 변수 'COMPlus_ZapDisable' '1'로 설정 하는 프로세스를 시작 하 여 미리 컴파일된 코드의 사용을 비활성화할 수 있습니다.

## <a name="see-also"></a>참고 항목  
 [Debugging Managed Code](../debugger/debugging-managed-code.md) (관리 코드 디버그)  
 [Navigating through Code with the Debugger](../debugger/navigating-through-code-with-the-debugger.md) (디버거로 코드 탐색)  
 [실행 중인 프로세스에 연결](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [관리되는 실행 프로세스](/dotnet/standard/managed-execution-process)
