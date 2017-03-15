---
title: "방법: 편집하며 계속하기 사용(C#) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "편집하며 계속하기[C#], 편집하며 계속하기 정보"
ms.assetid: 40e136d8-a08c-43bd-b313-fb821c55eb3c
caps.latest.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 19
---
# 방법: 편집하며 계속하기 사용(C#)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

C\#에서 편집하며 계속하기를 사용하면 디버깅하는 동안 중단 모드에서 코드를 변경할 수 있습니다.  디버깅 세션을 중지하고 다시 시작하지 않고도 변경 내용을 적용할 수 있습니다.  
  
 편집하며 계속하기는 중단 모드에서 필요한 내용을 변경한 다음 **계속**, **단계** 또는 **다음 문 설정** 같은 디버거 실행 명령을 선택하거나 디버거 창에서 함수를 실행하는 경우에 자동으로 호출됩니다.  
  
> [!NOTE]
>  Compact Framework, 최적화된 코드, 혼합된 네이티브\/관리 코드 또는 SQL Server CLR\(공용 언어 런타임\) 통합 코드를 디버깅할 때는 편집과 계속하기가 지원되지 않습니다.  이러한 시나리오 중 하나에서 코드 변경 내용을 적용하려고 하면 디버거에서 편집하며 계속하기가 지원되지 않는다는 대화 상자를 표시합니다.  
  
### 편집하며 계속하기를 자동으로 호출하려면  
  
1.  중단 모드에서 소스 코드를 변경합니다.  
  
2.  **디버그** 메뉴에서 **계속**, **단계** 또는 **다음 문 설정**을 클릭하거나 디버거 창에서 함수를 실행합니다.  
  
     새 코드가 컴파일되고 새 코드를 사용하여 디버깅이 계속 진행됩니다.  일부 변경 사항은 편집하며 계속하기에서 지원되지 않습니다.  자세한 내용은 [지원되는 코드 변경\(C\#\)](../debugger/supported-code-changes-csharp.md)을 참조하십시오.  
  
### 편집하며 계속하기를 사용하거나 사용하지 않도록 설정하려면  
  
1.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
2.  **옵션** 대화 상자에서 **디버깅** 노드를 확장하고 **편집하며 계속하기**를 선택합니다.  
  
3.  **옵션** 대화 상자의 **편집하며 계속하기** 페이지에서 **편집하며 계속하기 사용** 확인란을 선택하거나 선택 해제합니다.  
  
     디버깅 세션을 다시 시작하면 설정 사항이 적용됩니다.  
  
## 참고 항목  
 [편집하며 계속하기\(Visual C\#\)](../debugger/edit-and-continue-visual-csharp.md)   
 [지원되는 코드 변경\(C\#\)](../debugger/supported-code-changes-csharp.md)   
 [편집하며 계속하기의 오류 및 경고\(C\#\)](../misc/edit-and-continue-errors-and-warnings-csharp.md)