---
title: "방법: 혼합 모드에서 디버깅 | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "디버깅[Visual Studio], 혼합 모드"
  - "DLL 디버깅"
  - "혼합 모드 디버깅"
ms.assetid: 2859067d-7fcc-46b0-a4df-8c2101500977
caps.latest.revision: 29
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 29
---
# 방법: 혼합 모드에서 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다음 절차에서는 관리 코드와 네이티브 코드를 모두 디버깅하는 방법에 대해 설명합니다. 이러한 디버깅을 혼합 모드 디버깅이라고도 합니다.  네이티브 코드로 작성된 것이 DLL인지 응용 프로그램인지 여부에 따라 혼합 모드 디버깅에는 두 가지 시나리오가 있습니다.  
  
-   DLL을 호출하는 호출 응용 프로그램이 네이티브 코드로 작성된 경우  DLL이 관리 코드로 작성된 것입니다. 이 경우 관리되는 디버거와 네이티브 디버거가 둘 모두를 디버깅할 수 있어야 합니다.  **\<Project\> 속성 페이지** 대화 상자에서 이를 확인할 수 있습니다.  이를 수행하는 방법은 DLL 프로젝트에서 디버깅을 시작하는지 아니면 호출 응용 프로그램 프로젝트에서 디버깅을 시작하는지에 따라 달라집니다.  
  
-   DLL을 호출하는 응용 프로그램이 관리 코드로 작성된 경우 DLL이 네이티브 코드로 작성된 것입니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 혼합 모드 디버깅을 사용하도록 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  
  
2.  **보기** 메뉴에서 **속성 페이지**를 클릭합니다.  
  
3.  **\<Project\> 속성 페이지** 대화 상자에서 **구성 속성** 노드를 확장하고 **디버깅**을 선택합니다.  
  
4.  **디버거 형식**을 **혼합** 또는 **자동**으로 설정합니다.  
  
## 참고 항목  
 [방법: DLL 프로젝트에서 디버깅](../debugger/how-to-debug-from-a-dll-project.md)