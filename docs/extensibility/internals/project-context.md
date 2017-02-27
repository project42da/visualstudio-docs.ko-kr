---
title: "프로젝트 컨텍스트 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "항목을 열면 프로젝트 [Visual Studio SDK]"
ms.assetid: d1803f4a-24eb-44b0-b5d2-cb40c15534be
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# 프로젝트 컨텍스트
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

사용자를 추가 하거나 프로젝트와 프로젝트 항목을 사용할 때 IDE 프로젝트 컨텍스트의 개념을 사용 하 여 확인 방법을 다양 한 작업을 수행 해야 합니다.  
  
 일반적으로 파일을 선택 하 여 사용자가 명시적으로 작성 하는 표준 프로젝트 개체입니다의  **새 프로젝트** 명령 또는 선택 하 여 사용할 수 있게는  **프로젝트 열기** 에  **파일** 메뉴.  이러한 경우 파일을 만들고 프로젝트의 컨텍스트 내에서 열린 한 프로젝트 종류의 문서 편집에 대 한 컨텍스트를 정의 합니다.  
  
 일부 프로젝트의 매우 다양 한 컨텍스트를 제공 합니다.  예를 들어, 프로젝트 프로젝트 범위, 프로그래밍 방식으로 네임 스페이스 또는 프로젝트 범위의 데이터베이스 연결에 대 한 데이터 바인딩 관리합니다.  사용자가 자주 파일 또는 데이터베이스 연결 프로젝트 항목이 솔루션 탐색기에 표시 된 것과 같은 특정 프로젝트 개체를 사용 하 여 직접 열 수 있습니다.  
  
 그러나 다른 프로젝트 컨텍스트 항목을 명시적으로 지정 되지 않습니다.  사용자를 선택 하 여 파일을 열 때 예를 들어 컨텍스트 항목을 사용할 수 없습니다의  **열기 기존 파일** 에  **파일** 메뉴에서 클릭할 때 또는 파일을 디버거 작동 되는  **파일에서 찾기** 명령에  **찾기 및 바꾸기** 대화 상자.  IDE 호출 이러한 상황을 처리 하도록 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument> 좋은 문서를 열려면 프로젝트를 찾는 과정을 관리 합니다.  
  
## 참고 항목  
 [프로젝트 우선 순위](../../extensibility/internals/project-priority.md)   
 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)