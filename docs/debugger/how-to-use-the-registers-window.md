---
title: "방법: 레지스터 창 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.registers"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "레지스터, 디버깅"
  - "레지스터 내용"
  - "플래그, 레지스터 창"
  - "레지스터 그룹"
  - "디버깅[Visual Studio], 레지스터 창"
  - "레지스터 창"
ms.assetid: 2918ffa2-562f-40d6-9053-ef321bbeb767
caps.latest.revision: 37
caps.handback.revision: 37
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 레지스터 창 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

레지스터 창은 **옵션** 대화 상자의 **디버깅** 노드에 있는 **일반** 범주에서 주소 수준 디버깅을 설정한 경우에만 사용할 수 있습니다.  
  
 **레지스터** 창에는 레지스터 내용이 표시됩니다.  프로그램을 단계별로 실행하면서 **레지스터** 창을 열어 두면 코드 실행에 따라 레지스터 값이 변경되는 것을 볼 수 있습니다.  최근에 변경된 값은 빨간색으로 표시됩니다.  레지스터 값은 편집할 수 있습니다.  자세한 내용은 [방법: 레지스터 값 편집](../debugger/how-to-edit-a-register-value.md)을 참조하십시오.  
  
 **레지스터** 창에서는 레지스터를 플랫폼 및 프로세서 유형에 따라 각각 다른 그룹으로 구성하여 간단하게 표시합니다.  레지스터 그룹은 사용자에게 맞게 표시하거나 숨길 수 있습니다.  자세한 내용은 [방법: 레지스터 그룹 표시 및 숨기기](../debugger/how-to-display-and-hide-register-groups.md)를 참조하십시오.  
  
 레지스터 및 레지스터 창의 개념에 대한 간략한 소개를 보려면 [디버깅 기본 사항: 레지스터 창](../debugger/debugging-basics-registers-window.md)을 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 레지스터 창을 표시하려면  
  
-   **디버그** 메뉴에서 **창**을 선택한 다음 **레지스터**를 선택합니다.  
  
     디버거는 실행 중이거나 중단 모드에 있어야 합니다.  
  
    > [!NOTE]
    >  스크립트나 SQL 응용 프로그램의 경우에는 레지스터 정보를 사용할 수 없습니다.  
  
## 참고 항목  
 [디버깅 기본 사항: 레지스터 창](../debugger/debugging-basics-registers-window.md)   
 [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)   
 [디버깅 기본 사항: 레지스터 창](../debugger/debugging-basics-registers-window.md)