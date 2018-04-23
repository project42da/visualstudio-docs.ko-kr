---
title: '오류: 함수를 계산 하는 동안 대상 프로세스가 종료 된 &#39;함수&#39; | Microsoft Docs'
ms.custom: ''
ms.date: 4/06/2018
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.process_exit_func_eval_abort
ms.technology: vs-ide-debug
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 620ff03ef364c21e20151547effe8bfbf5935fe7
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="error-the-target-process-exited-while-evaluating-the-function-39function39"></a>오류: 함수를 계산 하는 동안 대상 프로세스가 종료 된 &#39;함수&#39;

전체 메시지 텍스트: 'function' 함수를 평가 하는 동안 대상 프로세스가 종료 되었습니다. 대상 프로세스의 종료 코드에 대 한 출력 창을 참조 하십시오.

.NET 개체의 상태를 검사 좀 더 쉽게 디버거에서 자동으로 새로 고쳐집니다 추가 코드를 실행 하는 디버깅 된 프로세스 (일반적으로 속성 getter 메서드 및 `ToString` 함수). 대부분의 시나리오에서 이러한 함수는 성공적으로 완료 하거나 디버거를 통해 수 있는 예외를 throw 합니다. 그러나는 예외가 없습니다 찾아낼 수 커널 경계를 교차, 사용자 메시지 펌프 필요로 하거나 복구할 수 없는 하기 때문에 몇 가지 경우가 있습니다. 결과, 속성 getter 또는 코드를 실행 하는 ToString 메서드 하나라도 명시적으로 프로세스를 종료 (예를 들어 호출 `ExitProcess()`) 수 있는 처리 되지 않은 예외를 throw 할 (예를 들어 `StackOverflowException`) 종료 됩니다는 디버깅 된 프로세스를 디버그 세션을 종료 합니다. 이 오류 메시지가 발생 하는 경우이 문제가 발생 합니다.
 
이 문제에 대 한 일반적인 이유 중 하나는 디버거는 자신을 호출 하는 속성을 계산 하는 경우 스택 오버플로 예외가 발생할 수 있습니다이 있습니다. 스택 오버플로 예외는 복구할 수 없습니다 및 대상 프로세스를 종료 합니다.
 
## <a name="to-correct-this-error"></a>이 오류를 해결하려면
 
이 문제와 가능한 해결 방법 두 가지가 있습니다.
 
### <a name="solution-1-prevent-the-debugger-from-calling-the-getter-property-or-tostring-method"></a>해결 방법 1: 속성 getter 또는 ToString 메서드 호출에서 디버거 방지 

오류 메시지에는 디버거를 호출 하려고 하는 함수의 이름을 알려줍니다. 함수 이름의 연습할 수에서 해당 함수를 다시 평가 **직접 실행** 창을 평가 디버그 합니다. 디버깅은에서 평가할 때 가능한는 **직접 실행** 창 하기 때문에 암시적 평가를 달리는 **자동/지역/조사식** 창, 디버거는 처리 되지 않은 예외에서 중단 합니다.

이 함수를 수정할 수 있는 경우 속성 getter 호출에서 디버거를 방지할 수 있습니다 또는 `ToString` 메서드. 다음 중 하나를 사용 하십시오.
 
* 방법 getter 속성 외에도 코드의 일부 다른 형식으로 변경 하거나 ToString 메서드 및 문제가 나타나지 것입니다.
    -또는-
* (에 대 한 `ToString`) 정의 `DebuggerDisplay` 유형과 하면에 특성 것 이외의 평가 디버거를 가질 수 `ToString`합니다.
    -또는-
* (예: 속성 getter) 배치는 `[System.Diagnostics.DebuggerBrowsable(DebuggerBrowsableState.Never)]` 속성에는 특성입니다. 이에 API 호환성을 위해 속성을 유지 해야 하는 메서드를 설정한 경우에 유용할 수 있습니다 있지만 메서드는 실제로 있어야 합니다.

이 메서드를 수정할 수 없는 경우 대체 명령에 대상 프로세스를 중단 하 고 계산을 다시 시도를 수 있습니다.
 
### <a name="solution-2-disable-all-implicit-evaluation"></a>해결 방법 2: 모든 암시적 계산이 사용 안 함
 
이전 솔루션의 문제를 해결 하지 않는 경우 이동 **도구** > **옵션**, 설정의 선택을 취소 **디버깅**  >   **일반** > **속성 확인 및 기타 암시적 함수 호출**합니다. 암시적 함수 평가 대부분 사용할 수 없게 됩니다 하 고 문제를 해결 해야 합니다.



  
