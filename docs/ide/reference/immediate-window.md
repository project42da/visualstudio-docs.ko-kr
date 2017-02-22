---
title: "직접 실행 창 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.ImmediateWindow"
helpviewer_keywords: 
  - "디자인 타임 식 계산"
  - "직접 실행 창"
  - "첫째 예외 알림"
ms.assetid: d33e7937-73f3-4c69-9df0-777a8713c6f2
caps.latest.revision: 24
caps.handback.revision: 24
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 직접 실행 창
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

**직접 실행** 창을 사용하여 식을 디버깅 및 계산하고, 문을 실행하며, 변수 값을 인쇄하는 등의 작업을 수행할 수 있습니다.  직접 실행 모드를 사용하면 디버깅 중 개발 언어에 의해 실행되거나 계산되는 식을 입력할 수 있으며,  **직접 실행** 창을 표시하려면 편집할 프로젝트를 연 다음 **디버그** 메뉴에서 **창**을 선택하고 **직접 실행**을 선택하거나 Ctrl\+ALT\+I를 누릅니다.  
  
 이 창을 사용하여 개별 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령을 실행할 수 있습니다.  사용 가능한 명령에는 값을 변수에 할당하는 데 사용할 수 있는 `EvaluateStatement`이 포함됩니다.  **직접 실행** 창에서는 또한 Intellisense도 지원합니다.  
  
## 변수 값 표시  
 이 창은 응용 프로그램을 디버깅하는 동안 특히 유용할 수 있습니다.  예를 들어, `varA` 변수의 값을 확인하려면 [인쇄 명령](../../ide/reference/print-command.md)을 사용합니다.  
  
```  
>Debug.Print varA  
```  
  
 물음표\(?\)는 `Debug.Print`의 별칭이므로 이 명령을 입력할 수도 있습니다.  
  
```  
>? varA  
```  
  
 이 명령의 두 버전 모두 `varA` 변수의 값을 반환합니다.  
  
> [!NOTE]
>  **직접 실행** 창에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령을 실행하려면 보다 큼 기호\(\>\)를 명령 앞에 사용해야 합니다.  여러 개의 명령을 입력하려면 **명령** 창으로 전환합니다.  
  
## 디자인 타임 식 계산  
 **직접 실행** 창을 사용하여 디자인 타임에 함수나 서브루틴을 실행할 수 있습니다.  
  
#### 디자인 타임에 함수를 실행하려면  
  
1.  다음 코드를 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 콘솔 응용 프로그램으로 복사합니다.  
  
    ```  
    Module Module1  
  
        Sub Main()  
            MyFunction(5)  
        End Sub  
  
        Function MyFunction(ByVal input as Integer) As Integer  
            Return input * 2  
        End Function  
  
    End Module  
    ```  
  
2.  **디버그** 메뉴에서 **창**을 클릭한 다음 **직접 실행**을 클릭합니다.  
  
3.  **직접 실행** 창에 `?MyFunction(2)`를 입력하고 Enter 키를 누릅니다.  
  
     **직접 실행** 창에서 `MyFunction`이 실행되고 `4`가 표시됩니다.  
  
 함수나 서브루틴에 중단점이 포함되어 있으면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]는 적절한 지점에서 실행을 중단합니다.  그런 다음 디버거 창을 사용하여 프로그램 상태를 검사할 수 있습니다.  자세한 내용은 [연습: 디자인 타임에 디버깅](../../debugger/walkthrough-debugging-at-design-time.md)를 참조하십시오.  
  
 [!INCLUDE[trprVSTOshort](../../ide/reference/includes/trprvstoshort_md.md)] 프로젝트, 웹 프로젝트, 스마트 장치 프로젝트 및 SQL 프로젝트를 비롯하여 실행 환경을 시작해야 하는 프로젝트 형식에는 디자인 타임 식 계산을 사용할 수 없습니다.  
  
### 다중 프로젝트 솔루션의 디자인 타임 식 계산  
 디자인 타임 식 계산을 위한 컨텍스트를 설정할 때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에서는 솔루션 탐색기에 현재 선택되어 있는 프로젝트를 참조합니다.  솔루션 탐색기에 프로젝트가 선택되어 있지 않으면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에서는 시작 프로젝트를 대상으로 함수를 계산합니다.  현재 컨텍스트에서 함수를 계산할 수 없으면 오류 메시지가 표시됩니다.  솔루션의 시작 프로젝트가 아닌 프로젝트에서 함수를 계산할 때 오류가 발생하면 솔루션 탐색기에서 프로젝트를 선택한 다음 다시 계산해 보십시오.  
  
## 명령 입력  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령을 **직접 실행** 창에서 실행할 때는 보다 큼 기호\(\>\)를 입력해야 합니다.  위쪽 화살표 및 아래쪽 화살표 키를 사용하여 전에 실행된 명령을 스크롤할 수 있습니다.  
  
|Task|해결책|예제|  
|----------|---------|--------|  
|식 계산|식 앞에 물음표\(?\)를 붙입니다.|`? a+b`|  
|직접 실행 모드에서 단일 명령을 실행하기 위해 임시로 명령 모드로 전환|보다 큼 기호\(\>\)를 앞에 사용하여 명령을 입력합니다.|`>alias`|  
|명령 창으로 전환|보다 큼 기호\(\>\)를 앞에 사용하여 창에 `cmd`를 입력합니다.|`>cmd`|  
|직접 실행 창으로 다시 전환|보다 큼 기호\(\>\)를 사용하지 않고 창에 `immed` 를 입력합니다.|`immed`|  
  
## 표시 모드  
 **직접 실행** 창에서 이전 줄을 클릭하면 자동으로 표시 모드로 전환됩니다.  표시 모드에서는 텍스트 편집기에서처럼 이전 명령의 텍스트를 선택, 편집 및 복사한 다음 현재 줄에 붙여넣을 수 있습니다.  
  
## 등호\(\=\)  
 `EvaluateStatement` 명령을 입력하는 데 사용되는 창은 등호\(\=\)가 비교 연산자로 해석되는지 아니면 할당 연산자로 해석되는지 결정합니다.  
  
 **직접 실행** 창에서는 등호\(\=\)가 할당 연산자로 해석됩니다.  예를 들어,  
  
```  
>Debug.EvaluateStatement(varA=varB)  
```  
  
 위의 명령은 `varA` 변수에 `varB` 변수의 값을 할당합니다.  
  
 반대로 **명령** 창에서는 등호\(\=\)가 비교 연산자로 해석됩니다.  **명령** 창에서는 할당 연산을 사용할 수 없습니다.  예를 들어, `varA` 및 `varB` 변수의 값이 다를 경우  
  
```  
>Debug.EvaluateStatement(varA=varB)  
```  
  
 위의 명령은 `False` 값을 반환합니다.  
  
## 첫째 예외 알림  
 일부 설정 구성에서는 첫째 예외 알림이 **직접 실행** 창에 표시됩니다.  
  
#### 직접 실행 창에 첫째 예외 알림이 표시되는지 여부를 전환하려면  
  
1.  **보기** 메뉴에서 **다른 창**을 클릭한 다음 **출력**을 클릭합니다.  
  
2.  **출력** 창의 텍스트 영역을 마우스 오른쪽 단추로 클릭하고 **예외 메시지**를 선택하거나 취소합니다.  
  
## 참고 항목  
 [디버거로 코드 탐색](../../debugger/navigating-through-code-with-the-debugger.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [Visual Studio의 디버깅](../../debugger/debugging-in-visual-studio.md)   
 [디버거 기본 사항](../../debugger/debugger-basics.md)   
 [연습: 디자인 타임에 디버깅](../../debugger/walkthrough-debugging-at-design-time.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)   
 [Visual Studio에서 정규식 사용](../../ide/using-regular-expressions-in-visual-studio.md)