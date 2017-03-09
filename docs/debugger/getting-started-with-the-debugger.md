---
title: "디버거 시작 | Microsoft Docs"
ms.custom: ""
ms.date: "12/08/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: c763d706-3213-494f-b4d2-990b6e1ec456
caps.latest.revision: 6
caps.handback.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 디버거 시작
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 디버거는 모든 언어에서 쉽게 사용할 수 있습니다.  여기서는 간단한 C\# 프로그램을 디버그하는 방법을 보여 주겠지만 C\+\+ 및 JavaScript와 같은 다른 언어의 코드에 동일한 단계를 적용할 수 있습니다.  
  
##  <a name="BKMK_Start_debugging_a_VS_project"></a> 기본 C\# 프로젝트 디버그  
 간단한 C\# 콘솔 응용 프로그램으로 시작하겠습니다\(**파일 \/ 새로 만들기 \/ 프로젝트**를 선택한 다음 **Visual C\#** 및 **콘솔 응용 프로그램**을 차례로 선택\).  이전에 Visual Studio를 사용한 적이 없을 경우 [연습: 간단한 응용 프로그램 만들기](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md)를 참조하세요.  Main 메서드는 정수 변수에 1을 10회 추가하고 결과를 콘솔에 출력합니다.  
  
```c#  
static void Main(string[] args)  
{  
    int testInt = 0;  
    for (int i = 1; i < 10; i++)  
    {  
        testInt += 1;  
    }  
    Console.WriteLine(testInt);  
}  
```  
  
 **디버그** 구성에서 이 코드를 빌드합니다.  이 구성은 기본적으로 설정되어 있습니다.  구성에 대한 자세한 내용은 [빌드 구성 이해](../ide/understanding-build-configurations.md)를 참조하세요.  
  
 **디버그 \/ 디버깅 시작**을 클릭하여\(또는 도구 모음에서 **시작**을 클릭하거나 F5 사용\) 디버거에서 이 코드를 실행합니다.  응용 프로그램이 거의 즉시 종료되므로 콘솔 창에 무엇인가 인쇄되었는지 여부는 사실 알 수 없습니다.  
  
 중단점을 설정한 다음 미리 단계별로 실행하면 콘솔 창을 보기에 충분한 시간 동안 실행을 중지할 수 있습니다.  중단점을 설정하려면 커서를 `Console.WriteLine` 줄에 놓고 **디버그 \/ 새 중단점 \/ 함수 중단점**을 클릭하거나 같은 줄에서 왼쪽 여백을 클릭하면 됩니다.  중단점은 다음과 같은 모습입니다.  
  
 ![중단점 설정](../debugger/media/getstartedbreakpoint.png "GetStartedBreakpoint")  
  
 중단점에 대한 자세한 내용은 [중단점 사용](../debugger/using-breakpoints.md)을 참조하세요.  
  
 다시 디버그를 시작합니다.  `Console.WriteLine` 코드가 실행되기 전에 실행이 중지됩니다.  미리 단계별로 실행되도록 지정하여 실행되게 할 수 있습니다\(**디버그 \/ 프로시저 단위 실행**을 클릭하거나 **F10** 사용\).  이 경우에는 **한 단계씩 코드 실행** \(**F11**\)을 선택하고 동일한 결과를 얻을 수도 있습니다. 그 차이는 나중에 설명하겠습니다.  메서드의 마지막 중괄호로 묶인 선이 노란색으로 변해야 합니다.  콘솔 창을 봅니다.  **10**이 표시되어야 합니다.  디버그를 중지합니다\(**디버그 \/ 디버깅 중지**, 또는 도구 모음에서 **디버깅 중지**, 또는 **SHIFT\+F5**\).  
  
 이제 변수 값을 살펴보겠습니다.  코드 창 바로 아래에 **자동**, **지역** 및 **조사식** 창이 표시됩니다.  이러한 창에는 실행 당시의 변수에 대한 현재 값이 표시됩니다.  **자동** 및 **지역** 창에는 값이 **10**인 testInt가 표시됩니다.  
  
 ![디버그할 때의 자동 창](../debugger/media/getstartedwindows.png "GetStartedWindows")  
  
 **자동** 및 **지역** 창에 대한 자세한 내용은 [변수 창](../Topic/Variable%20Windows.md)을 참조하세요.  
  
 프로그램을 진행함에 따라 변수 값이 어떻게 변경되는지 살펴보겠습니다.  `testInt += 1;` 줄에 중단점을 설정하고 디버그를 시작합니다.  **지역** 및 **자동** 창의 **testInt**가 **0**으로, **i**가 **1**로 표시되어야 합니다.  디버그를 계속할 경우\(**디버그 \/ 계속**, 또는 도구 모음의 **계속** 또는 **F5**\), testInt의 값이 **1**로 변경되고, 그 다음에 **2** 등으로 변경되는 것을 볼 수 있습니다.  이러한 변경 내용을 보는 것이 힘들면 중단점을 제거\(**디버그 \/ 중단점 설정\/해제**, 또는 여백에서 해당 중단점 클릭\)하고 디버그를 계속하세요.  모든 중단점을 제거하려면 **디버그 \/ 모든 중단점 삭제**를 클릭하거나 **CTRL \+ SHIFT \+ F9**를 누르고, **모든 중단점을 제거하시겠습니까?**라고 묻는 대화 상자에서 **예**를 클릭합니다.  
  
## 함수 호출을 한 단계씩 코드 실행 및 프로시저 단위 실행  
 **한 단계씩 코드 실행**과 **프로시저 단위 실행** 간의 차이를 알려면 다른 메서드에 의해 호출되는 메서드를 추가해야 합니다.  C\# 응용 프로그램에 메서드를 추가하고 Main 메서드에서 호출합니다.  코드는 다음과 비슷합니다.  
  
```c#  
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
  
 Main 메서드에서 `Method1();` 호출에 중단점을 설정하고 디버그를 시작합니다.  실행이 중단되면 **디버그 \/ 한 단계씩 코드 실행**\(또는 도구 모음에서 **한 단계씩 코드 실행**, 또는 **F11** 사용\)을 클릭합니다.  Method1\(\)의 첫 번째 중괄호에서 실행이 다시 중단됩니다.  
  
 ![한 단계씩 코드 실행](../debugger/media/getstartedstepinto.png "GetStartedStepInto")  
  
 디버그를 중지했다가 다시 시작하고, 실행이 중단점에서 중단되면 **디버그\/ 프로시저 단위 실행**\(또는 도구 모음에서 **프로시저 단위 실행**, 또는 **F10** 사용\)을 클릭합니다.  실행이 `Console.WriteLine("end");`에서 다시 중단됩니다.  
  
 디버거를 사용한 코드 탐색에 대해 자세히 알려면, [디버거로 코드 탐색](../debugger/navigating-through-code-with-the-debugger.md)을 참조하세요.