---
title: "Visual Studio에서 계층 구조 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "계층 구조, Visual Studio IDE"
  - "IDE, 계층 구조"
ms.assetid: 0a029a7c-79fd-4b54-bd63-bd0f21aa8d30
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# Visual Studio에서 계층 구조
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\)으로 프로젝트를 표시 한  *계층 구조*.  IDE에서 계층의 각 노드는 일련의 연결 된 속성에 있는 노드를 트리입니다.  A  *프로젝트 계층 구조* 프로젝트의 항목, 항목의 관계를 한 항목의 연결 된 속성 및 명령을 보유 하는 컨테이너입니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 계층 인터페이스를 사용 하면 프로젝트 계층 구조를 관리 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 인터페이스 명령을 표준 명령 처리기 대신 해당 계층 구조 창에서 프로젝트 항목을 호출을 리디렉션합니다.  
  
## 프로젝트 계층 구조  
 각 프로젝트 계층 구조 보기 및 편집할 수 있는 항목을 포함 합니다.  이러한 항목은 프로젝트 형식에 따라 다릅니다.  예를 들어, 데이터베이스 프로젝트에 저장된 프로시저, 뷰 데이터베이스 및 데이터베이스 테이블 포함 될 수 있습니다.  프로그래밍 언어 프로젝트는 반면, 소스 파일 및 비트맵 및 대화 상자에 대 한 리소스 파일을 가능성이 포함 됩니다.  프로젝트 계층 구조를 만들 때 일부 유연성 결과 계층 구조가 중첩 될 수 있습니다.  
  
 새 프로젝트 형식을 만들 때 프로젝트 유형에서 편집할 수 있는 항목의 전체 집합을 제어 합니다.  그러나 프로젝트에 대 한 이러한 편집을 지원 하지 않은 항목을 포함할 수 있습니다.  예를 들어, Visual c \+ \+ HTML 파일 형식에 대해 사용자 지정 된 편집기를 제공 하지 않는 경우에 Visual c \+ \+ 프로젝트에 HTML 파일이 포함할 수 있습니다.  
  
 지 속성을 포함 하는 항목의 계층 구조를 관리 합니다.  계층의 구현 계층 내에서 항목의 지 속성에 영향을 주는 특수 한 속성을 제어 해야 합니다.  예를 들어, 개체 저장소에 있는 파일의 항목을 나타내는 경우 계층 구현 개체의 지 속성을 제어 해야 합니다.  항목에 사용자 입력을 저장 하는 계층 구조는 IDE를 지시 하지만 IDE에서 이러한 항목을 저장 하는 데 필요한 모든 작업을 제어 하지 않습니다.  대신 프로젝트에 컨트롤입니다.  
  
 사용자가 편집기에서 항목을 열 때 그 항목을 제어 하는 계층 선택 되 고 현재 계층 됩니다.  선택한 계층 항목에 역할을 할 수 있는 명령 집합을 결정 합니다.  사용자가 포커스를 이런 방식이으로 추적 사용자의 현재 컨텍스트를 반영 하는 계층 구조 수 있습니다.  
  
## 참고 항목  
 [프로젝트 형식](../../extensibility/internals/project-types.md)   
 [선택 및 IDE에서 통화](../../extensibility/internals/selection-and-currency-in-the-ide.md)   
 [VSSDK 샘플](../../misc/vssdk-samples.md)