---
title: "편집하며 계속하기(Visual Basic) | Microsoft Docs"
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
  - "VB"
helpviewer_keywords: 
  - "64비트 편집하며 계속하기"
  - "디버깅[Visual Basic], 편집하며 계속하기"
  - "편집하며 계속하기[Visual Basic]"
  - "편집하며 계속하기, 64비트"
  - "Visual Basic, 편집하며 계속하기"
ms.assetid: 7e90f34f-e699-45ab-a4c9-a4b527c498c8
caps.latest.revision: 40
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 40
---
# 편집하며 계속하기(Visual Basic)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 디버깅의 편집하며 계속하기 기능을 사용하면 코드가 중단 모드에서 실행되는 동안 코드를 변경할 수 있습니다.  코드 편집을 적용한 후에 새 편집 내용이 적용된 상태로 코드 실행을 다시 시작하고 그 결과를 확인할 수 있습니다.  
  
 편집하며 계속하기 기능은 중단 모드를 시작할 때마다 사용할 수 있습니다.  중단 모드에서 소스 창에 노란색 화살표로 표시되는 명령 포인터는 다음에 실행할 줄을 가리키며 메서드 또는 속성 본문 내의 실행문에 위치합니다.  중단 모드에서 실행문에 대한 거의 모든 종류의 변경 작업을 수행할 수 있고 이 변경 내용은 내부 프로젝트에 통합됩니다.  그러나 중단 모드에서 공용 메서드, 공용 필드 또는 클래스 선언 같은 선언문에 대한 변경은 일반적으로 허용되지 않습니다.  
  
 허용되지 않는 편집 작업을 수행하면 변경 내용 아래에 자주색 물결선이 표시되고 작업 목록에 이 작업이 나타납니다.  편집하며 계속하기를 진행하려면 허용되지 않는 편집 작업을 취소해야 합니다.  편집하며 계속하기 외부에서는 허용되지 않는 특정 작업이 허용될 수도 있습니다.  이러한 허용되지 않는 편집의 결과를 유지하려면 디버깅을 중지하고 응용 프로그램을 다시 시작해야 합니다.  
  
 편집하며 계속하기는 .NET Framework 4.5.1을 대상으로 하는 64비트 프로젝트에 대해 지원됩니다.  
  
 **프로세스에 연결**을 사용하여 디버깅을 시작하는 경우에는 편집하며 계속하기가 지원되지 않습니다.  최적화된 코드, 혼합된 관리 및 네이티브 코드 또는 Compact Framework\(스마트 장치\) 프로젝트에는 편집하며 계속하기가 지원되지 않습니다.  
  
 이 단원의 항목에서는 이 기능을 사용하는 방법과 허용되지 않는 종류의 변경에 대한 자세한 내용을 제공합니다.  
  
## 단원 내용  
 [방법: 편집하며 계속하기를 사용하여 중단 모드에서 편집 적용](../debugger/how-to-apply-edits-in-break-mode-with-edit-and-continue.md)  
 중단 모드에서 코드 편집 내용을 적용하는 방법에 대해 설명합니다.  
  
 [Visual Basic 편집하며 계속하기에서 지원되지 않는 편집](../debugger/unsupported-edits-in-visual-basic-edit-and-continue.md)  
 [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)] 편집하며 계속하기에서 수행할 수 없는 편집 유형에 대해 설명합니다.  
  
## 관련 단원  
 [편집하며 계속하기](../debugger/edit-and-continue.md)  
 편집하며 계속하기에 대한 항목 목록을 제공합니다.