---
title: "선택 및 IDE에서 통화 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "통화, Visual Studio IDE"
  - "IDE에서 선택"
  - "선택 항목을 Visual Studio IDE"
  - "IDE, 통화"
ms.assetid: 2f6f18d1-acd8-454d-a856-9a4d81155052
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# 선택 및 IDE에서 통화
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\) 선택을 사용 하 여 현재 선택한 개체에 대 한 사용자의 정보를 유지 관리 *컨텍스트*합니다. 선택 컨텍스트와 VSPackages에에서 참가할 수 있습니다 통화 두 가지 방법으로 추적 합니다.  
  
-   IDE에 Vspackage에 대 한 통화 정보를 전파 하 여 합니다.  
  
-   IDE 내에서 사용자의 현재 선택 항목을 모니터링 합니다.  
  
## 선택 영역 컨텍스트  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE 전체적으로 추적 IDE 자체 전역 선택 context 개체에는 통화입니다. 다음 표에서 선택 컨텍스트를 구성 하는 요소를 보여 줍니다.  
  
|요소|설명|  
|--------|--------|  
|현재 계층 구조|일반적으로 현재 프로젝트입니다. NULL 현재 계층 구조 전체 솔루션 현재 임을 나타냅니다.|  
|현재 ItemID|현재 계층 구조 내에서 선택한 항목 프로젝트 창에서 여러 항목을 선택할 경우 현재 항목을 여러 개 있을 수 있습니다.|  
|현재 `SelectionContainer`|속성 창의 속성을 표시 하는 하나 이상의 개체를 보유 합니다.|  
  
 또한 환경에는 두 전역 목록을 유지 관리합니다.  
  
-   현재 UI 명령 식별자 목록  
  
-   현재 활성 요소 형식의 목록입니다.  
  
### 창 유형 및 선택  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE에서는 두 가지 일반 유형으로 windows를 구성 합니다.  
  
-   계층 유형을 windows  
  
-   도구 창과 문서 창 같은 프레임 창  
  
 IDE 이러한 각 유형의 창에 대 한 통화를 다르게 추적합니다.  
  
 가장 일반적인 프로젝트 형식 IDE 제어 하는 솔루션 탐색기입니다. 현재 계층 구조를 결정 하기 위한 사용자의 선택에 의존 하는 창 및 프로젝트 형식 창 글로벌 계층 및 ItemID 전역 선택 컨텍스트를 추적 합니다. 프로젝트 형식 창에 대 한 환경 제공 글로벌 서비스 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>, 을 통해 어떤 Vspackage 열려 요소에 대 한 현재 값을 모니터링할 수 있습니다. 환경에서 탐색 속성은이 글로벌 서비스에 의해 좌우 됩니다.  
  
 프레임 창은 DocObject 프레임 창 내에서 선택 영역 컨텍스트 값 \(계층 구조\/ItemID\/SelectionContainer 같이\)를 푸시하기 위해 반면에 사용 합니다. 입니다. 서비스를 사용 하는 프레임 창 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> 이 목적을 위해. DocObject 수 푸시 선택 컨테이너에 대 한 값만 계층에 대 한 로컬 값을 유지 및 MDI 자식 문서에 대 한 보통의 ItemID 변경 합니다.  
  
### 이벤트 및 통화  
 두 가지 유형의 이벤트에는 통화의 환경의 개념에 영향을 주는 발생할 수 있습니다.  
  
-   전역 수준으로 전파 되 고 창 프레임 선택 컨텍스트를 변경 하는 이벤트입니다. 이러한 종류의 이벤트의 예로 MDI 자식 창이 열려 전역 도구 창 또는 열려는 프로젝트 형식 도구 창을 열려 있습니다.  
  
-   창 프레임 선택 컨텍스트 내에서 추적 하는 요소를 변경 하는 이벤트입니다. 프로젝트 형식 창에서 선택한 항목을 변경 하거나 DocObject 내에서 선택 영역을 예로 들 수 있습니다.  
  
## 참고 항목  
 [컨텍스트 개체 선택](../../extensibility/internals/selection-context-objects.md)   
 [사용자에 게 피드백](../../extensibility/internals/feedback-to-the-user.md)