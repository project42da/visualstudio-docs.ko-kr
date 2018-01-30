---
title: "Visual Studio의 디버거 시작 | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 02/07/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: get-started-article
ms.assetid: 0b3138c4-b840-446a-a15c-10ed8e2dd050
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 171b07d453c81883354848f70458bab39daa313e
ms.sourcegitcommit: 9a2f937e42305db6e3eaa7aadc235b0ba9aafc83
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2018
---
# <a name="get-started-with-the-visual-studio-debugger"></a>Visual Studio 디버거 시작
Visual Studio 디버거는 모든 언어에서 쉽게 사용할 수 있습니다. 간단한 C# 프로그램을 디버깅 하는 방법을 보여 주 겠지만 여기 하지만 c + + 및 JavaScript와 같은 다른 언어의 코드에 동일한 단계를 적용할 수 있습니다.

유사한 기능을 보여 주는 비디오를 시청 하려면 [디버거 시작](https://www.youtube.com/watch?v=FtGCi5j30YU&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=6)합니다.
  
##  <a name="BKMK_Start_debugging_a_VS_project"></a>기본 C# 프로젝트 디버깅  
 간단한 C# 콘솔 응용 프로그램으로 시작 하겠습니다 (**파일 > 새로 만들기 > 프로젝트**을 선택한 후 **Visual C#** 차례로 **콘솔 응용 프로그램**). 이전에 Visual Studio 사용한 적, 참조 [연습: 간단한 응용 프로그램 만들기](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md)합니다. **Main** 메서드 방금 10 회를 정수 변수에 1을 추가 하 고 결과를 콘솔에 출력 합니다.  
  
```csharp  
static void Main(string[] args)  
{  
    int testInt = 0;  
    for (int i = 1; i <= 10; i++)  
    {  
        testInt += 1;  
    }  
    Console.WriteLine(testInt);  
}  
```  
  
 이 코드를 작성은 **디버그** 구성 합니다. 이 구성은 기본적으로 설정되어 있습니다. 구성에 대 한 자세한 내용은 참조 [빌드 구성 이해](../ide/understanding-build-configurations.md)합니다.  
  
 디버거에서이 코드를 클릭 하 여 실행 **디버그 > 디버깅 시작** (또는 **시작** 도구 모음 또는 **F5**). 응용 프로그램이 거의 즉시 종료 되므로 콘솔 창에서 모든 항목을 인쇄 되었는지 여부는 사실 알 수 없습니다.  
  
 중단점을 설정한 다음 미리 단계별로 실행하면 콘솔 창을 보기에 충분한 시간 동안 실행을 중지할 수 있습니다. 중단점을 설정 하려면에 커서를 놓습니다는 `Console.WriteLine` 슬롯과 클릭 **디버그 > 새 중단점 > 함수 중단점**, 같은 줄에서 왼쪽 여백을 클릭 하거나 합니다. 중단점은 다음과 같은 모습입니다.  
  
 ![중단점을 설정](../debugger/media/getstartedbreakpoint.png "GetStartedBreakpoint")  
  
 중단점에 대 한 자세한 내용은 참조 [를 사용 하 여 중단점](../debugger/using-breakpoints.md)합니다.  
  
##  <a name="BKMK_Inspect_Variables"></a>변수 검사  
 특정 지점에서 원하는 값을 포함 하지 않는 변수를 찾는 종종 디버깅 작업이 포함 됩니다. 일부의 변수를 검사할 수 제공 됩니다.  
  
 다시 디버그를 시작합니다. `Console.WriteLine` 코드가 실행되기 전에 실행이 중지됩니다. 미리 단계별로 실행 하 여 실행 되 게 할 수 있습니다 (클릭 **디버그 > 프로시저 단위 실행** 또는 **F10**). 이 경우 선택할 수 있습니다 **한 단계씩 코드 실행** (**F11**)는 동일한 결과 얻을 차이 나중에 설명 하겠습니다. 메서드의 마지막 중괄호로 묶인 선이 노란색으로 변해야 합니다. 콘솔 창을 봅니다. 표시 되어야 **10**합니다.  
  
 가리키면 수는 **testInt** 데이터 팁에서 현재 값을 확인 하는 변수입니다.  
  
 ![DBG&#95;Basics&#95;Data&#95;Tips](../debugger/media/dbg_basics_data_tips.png "DBG_Basics_Data_Tips")  
  
 코드 창 바로 아래 표시 됩니다는 **자동**, **지역**, 및 **조사식** windows 합니다. 이러한 창에는 실행 당시의 변수에 대한 현재 값이 표시됩니다. 두는 **자동** 및 **지역** windows 표시 **testInt** 값 **10**합니다.  
  
 ![자동 창 디버깅할 때](../debugger/media/getstartedwindows.png "GetStartedWindows")  
  
 이러한 기간에 대 한 자세한 내용은 참조 [자동 및 지역 창](../debugger/autos-and-locals-windows.md)합니다.  
  
 프로그램을 통해 진행 함에 따라 변수 값이 어떻게 변경 되는지 살펴보겠습니다. 에 중단점을 설정는 `testInt += 1;` 슬롯과 디버깅을 다시 시작 합니다. 확인할 **testInt** 에 **지역** 및 **자동** windows가 **0**, 및 **i** 는**1**합니다. 디버깅 계속 (**디버그 > 계속**, 또는 **계속** 도구 모음의 또는 **F5**), 함을 확인할 수 있습니다 값 **testInt** 변경 내용 **1**, 다음 **2**등입니다. 이러한 변경 내용을 보는의 힘들 면 중단점을 제거 (**디버그 > 중단점 설정/해제**, 여백을 클릭 하거나), 디버깅을 계속 합니다. 모든 중단점을 제거 하려면 클릭 **디버그 > 모든 중단점 삭제**, 또는 **CTRL + SHIFT + F9**를 클릭 하 고 **예** 를 묻는 대화 상자에서 **수행 모든 중단점을 제거 하 시겠습니까?** .  
  
## <a name="stepping-into-and-over-function-calls"></a>함수 호출을 한 단계씩 코드 실행 및 프로시저 단위 실행  
 Debugger 문-여-문은에서 코드를 실행할 수 있습니다 (**한 단계씩 코드 실행**) 하거나 디버거에서 함수를 생략 하는 동안 코드를 실행할 수 있습니다 (**프로시저 단위 실행**) (에서 더 많은 관심 하는 코드를 빠르게 함수 코드 여전히 실행). 두 메서드 모두 동일한 디버깅 세션에서 간에 전환할 수 있습니다.  
  
 간의 차이 보려면 **한 단계씩 코드 실행** 및 **프로시저 단위 실행**, 다른 메서드에 의해 호출 되는 메서드를 추가 해야 합니다. C# 응용 프로그램에 메서드를 추가하고 Main 메서드에서 호출합니다. 코드는 다음과 비슷합니다.  
  
```csharp  
static void Main(string[] args)  
{  
    Method1();  
    Console.WriteLine("end");  
}  
  
private static void Method1()  
{  
    Console.WriteLine("in Method1");  
}  
```  
  
 Main 메서드에서 `Method1();` 호출에 중단점을 설정하고 디버그를 시작합니다. 실행이 중단 되 면 클릭 **디버그 > 한 단계씩 코드 실행** (또는 **한 단계씩 코드 실행** 도구 모음 또는 **F11**). Method1()의 첫 번째 중괄호에서 실행이 다시 중단됩니다.  
  
 ![코드를 한 단계씩 실행](../debugger/media/getstartedstepinto.png "GetStartedStepInto")  
  
 디버깅을 중지, 다시 시작 하 고 실행이 중단점에서 중단 하는 경우 클릭 **디버그 > 프로시저 단위 실행** (또는 **프로시저 단위 실행** 도구 모음 또는 **F10**). 실행이 `Console.WriteLine("end");`에서 다시 중단됩니다.  
  
 디버거를 사용 하 여 코드를 탐색 하는 방법에 대 한 자세한 내용을 참조 하십시오. 하려면 [디버거로 코드 탐색](../debugger/navigating-through-code-with-the-debugger.md)합니다.