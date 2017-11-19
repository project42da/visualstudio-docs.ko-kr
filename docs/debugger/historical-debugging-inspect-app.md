---
title: "기록 디버깅을 사용 하 여 앱 검사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 629b5d93-39b2-430a-b8ba-d2a47fdf2584
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 10d9e23912da2ee5d0af1b6d2f846fa1de2f94fe
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="inspect-your-app-with-intellitrace-historical-debugging-in-visual-studio"></a>기록 디버깅 Visual Studio에서 IntelliTrace로 앱을 검사 합니다.
사용할 수 있습니다 [기록 디버깅](../debugger/historical-debugging.md) 하 뒤로 이동 하 고 응용 프로그램의 실행 도중 앞의 상태를 검사 합니다.  
  
Visual Studio Enterprise edition Professional 또는 Community edition 아님에서 IntelliTrace를 사용할 수 있습니다.  
  
## <a name="navigate-your-code-with-historical-debugging"></a>기록 디버깅을 사용 하 여 코드 탐색  
 버그가 있는 간단한 프로그램부터 살펴보겠습니다. C# 콘솔 응용 프로그램에서 다음 코드를 추가합니다.  
  
```CSharp  
static void Main(string[] args)  
{  
    int testInt = 0;  
    int resultInt = AddAll(testInt);  
    Console.WriteLine(resultInt);  
}  
private static int AddAll(int j)  
{  
    for (int i = 0; i < 20; i++)  
    {  
        j = AddInt(j);  
    }  
    return j;  
}  
  
private static int AddInt(int add)  
{  
    if (add == 10)  
    {  
        return add += 25;  
    }  
    return ++add;  
}  
```  
  
 으로 가정 하겠습니다의 예상 값 `resultInt` 호출한 후 `AddAll()` 는 20 개입니다 (증분 한 결과 `testInt` 20 배). (또한에서는의 버그를 볼 수 없는 `AddInt()`). 하지만 결과 실제로 44입니다. `AddAll()`을 단계적으로 10회 실행하지 않고도 버그를 찾으려면 어떻게 할까요? 기록 디버깅 빠르고 쉽게 버그를 찾지를 사용할 수 있습니다. 방법은 다음과 같습니다.  
  
1.  **도구 > 옵션 > IntelliTrace > 일반**IntelliTrace 설정 되어 있는지 확인 하 고 선택 **IntelliTrace 이벤트 및 호출 정보**합니다. 이 옵션을 선택하지 않으면 탐색 여백(아래 설명)을 볼 수 없습니다.  
  
2.  `Console.WriteLine(resultInt);` 줄에 중단점을 설정합니다.  
  
3.  디버깅을 시작합니다. 코드가 중단점까지 실행됩니다. 에 **지역** 창 함을 확인할 수 있습니다 값 `resultInt` 44입니다.  
  
4.  열기는 **진단 도구** 창 (**디버그 > 진단 도구 표시**). 코드 창이 다음과 같이 나타납니다.  
  
     ![중단점에서 코드 창](../debugger/media/historicaldebuggingbreakpoint.png "HistoricalDebuggingBreakpoint")  
  
5.  중단점 바로 위 왼쪽 여백 옆에 이중 화살표가 표시됩니다. 이 영역은 탐색 여백 이라고 하 고 기록 디버깅에 사용 됩니다. 화살표를 클릭합니다.  
  
     코드 창에서 위 코드 줄(`int resultInt = AddIterative(testInt);`)에 분홍색이 지정된 것을 확인할 수 있습니다. 창 위에 현재 위치는 기록 디버깅 하는 메시지가 표시 됩니다.  
  
     이제 코드 창의 모양은 다음과 같습니다.  
  
     ![기록 디버깅 모드에서 코드 창](../debugger/media/historicaldebuggingback.png "HistoricalDebuggingBack")  
  
6.  한 단계씩 실행할 수 이제는 `AddAll()` 메서드 (**F11**, 또는 **한 단계씩 코드 실행** 탐색 여백에는 단추입니다. 으로 이동 (**F10**, 또는 **다음 호출로 이동** 탐색 여백에 있습니다. 분홍색 줄이 `j = AddInt(j);` 줄에 표시됩니다. **F10** 이 경우 코드의 다음 줄으로 진행 하지 않습니다. 대신, 다음 함수 호출로 이동합니다. 기록 디버깅은 여러 호출을 탐색하며 함수 호출이 포함되지 않은 코드 줄을 건너뜁니다.  
  
7.  이제 `AddInt()` 메서드를 한 단계씩 실행합니다. 이 코드의 버그가 즉시 표시됩니다.  

## <a name="next-steps"></a>다음 단계

이 절차 기초적 으로만 기록 디버깅으로 수행할 수 있는 작업입니다.

- 디버깅 하는 동안 스냅숏을 보려면를 참조 하세요. [IntelliTrace 단계 백을 사용 하 여 스냅숏 보기](../debugger/how-to-use-intellitrace-step-back.md)합니다.
- 다양 한 설정 및 탐색 여백에 있는 여러 단추의 효과 대해 자세히 알아보려면 참조 [IntelliTrace 기능](../debugger/intellitrace-features.md)합니다.