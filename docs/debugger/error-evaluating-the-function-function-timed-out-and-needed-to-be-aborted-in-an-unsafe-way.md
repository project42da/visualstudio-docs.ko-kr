---
title: "함수 &#39; 함수 &#39; 오류: 평가 초과 하는 안전 하지 않은 방식으로 중단 하는 데 필요한 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.error.unsafe_func_eval_abort
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ff5dedb9bf0ffe44ec1a7c031d4c1d0eeeea08ec
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="error-evaluating-the-function-39function39-timed-out-and-needed-to-be-aborted-in-an-unsafe-way"></a>함수 &#39; 함수 &#39; 오류: 평가 초과 하는 안전 하지 않은 방식으로 중단 하는 데 필요한

전체 메시지 텍스트: 시간 초과 및 안전 하지 않은 방식으로 중단 하는 데 필요한 'function' 함수를 계산 합니다. 대상 프로세스를 손상 있을 수 있습니다. 

쉽게.NET 개체의 상태를 검사 디버거에서 자동으로 새로 고쳐집니다 디버깅된 된 프로세스를 (일반적으로 속성 getter 메서드 및 ToString 함수)에 추가 코드를 실행 합니다. 대부분의 모든 시나리오에서 이러한 함수는 신속 하 게 완료 하 고 디버깅을 훨씬 쉽게 확인 합니다. 그러나 디버거는 샌드박스에서 응용 프로그램을 실행 되지 않습니다. 결과적으로, 속성 getter 또는 중단 하는 네이티브 함수를 호출 하는 ToString 메서드를 복구할 수 없을 수 있는 긴 시간 제한 될 수 있습니다. 이 오류 메시지가 발생 하는 경우이 문제가 발생 합니다.
 
이 문제에 대 한 일반적인 이유 중 하나는 디버거에서 계산 속성을 때만 실행 검사 중인 스레드를 수 있다는 점입니다. 따라서 디버깅 된 응용 프로그램 내에서 실행 되도록 다른 스레드에서 대기 하는 속성 및.NET 런타임을 중단할 수 없는 방식으로 대기 하는 경우이 문제가 발생 합니다.
 
## <a name="to-correct-this-error"></a>이 오류를 해결하려면
 
이 문제와 가능한 해결 방법을 세 가지가 있습니다.
 
### <a name="solution-1-prevent-the-debugger-from-calling-the-getter-property-or-tostring-method"></a>해결 방법 1: 속성 getter 또는 ToString 메서드 호출에서 디버거 방지
 
오류 메시지에는 디버거를 호출 하려고 함수의 이름을 알려줍니다. 이 함수를 수정할 수 있는 경우에 속성 getter 또는 ToString 메서드 호출에서 디버거를 방지할 수 있습니다. 다음 중 하나를 사용 하십시오.
 
* 방법 getter 속성 외에도 코드의 일부 다른 형식으로 변경 하거나 ToString 메서드 및 문제가 나타나지 것입니다.
    또는
* (ToString)에 대 한 형식에 DebuggerDisplay 특성을 정의 하 고 평가 ToString 이외의 디버거를 사용할 수 있습니다.
    또는
* (예: 속성 getter) 배치는 `[System.Diagnostics.DebuggerBrowsable(DebuggerBrowsableState.Never)]` 속성에는 특성입니다. 이 API 호환성을 위해 속성 상태로 유지 해야 하는 메서드를 설정한 경우에 유용할 수 있습니다 하지만 메서드가 실제로 이어야 합니다.
 
### <a name="solution-2-have-the-target-code-ask-the-debugger-to-abort-the-evaluation"></a>해결 방법 2: 계산을 중단 하도록 디버거를 요청 하는 대상 코드를 있는
 
오류 메시지에는 디버거를 호출 하려고 함수의 이름을 알려줍니다. 속성 getter 또는 ToString 메서드가 실패 합니다. 제대로 실행 되도록 하려면,이 문제가 되는 경우에 특히 코드에 다른 스레드가 코드를 실행 하려면 필요한 경우 구현 함수를 호출할 수 `System.Diagnostics.Debugger.NotifyOfCrossThreadDependency` 함수를 중단 하도록 디버거를 요청 하기 평가 합니다. 이 솔루션을 여전히 명시적으로 이러한 함수를 평가할 수는 있지만 기본 동작은 NotifyOfCrossThreadDependency 호출이 발생 하면 실행이 중지 합니다.
 
### <a name="solution-3-disable-all-implicit-evaluation"></a>해결 방법 3: 모든 암시적 계산이 사용 안 함
 
이전 솔루션의 문제를 해결 하지 않는 경우 이동 *도구* > *옵션*, 설정의 선택을 취소 *디버깅*  >   *일반* > *속성 확인 및 기타 암시적 함수 호출*합니다. 암시적 함수 평가 대부분 사용할 수 없게 됩니다 하 고 문제를 해결 해야 합니다.



  
