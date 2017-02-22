---
title: "IntelliSense 호스팅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-IntelliSense 호스팅"
ms.assetid: 20c61f8a-d32d-47e2-9c67-bf721e2cbead
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# IntelliSense 호스팅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio IntelliSense를 호스팅할 수 있습니다.  호스팅 사용 수 있습니다 IntellSense IntelliSense Visual Studio 텍스트 편집기에서 호스트 되지 않는 코드를 제공 합니다.  
  
## IntelliSense 호스팅 사용 현황  
 Visual Studio 완성 세트와 텍스트 버퍼에 액세스 하는 코드 IntelliSense windows 모든 위치에서 구할 수 있습니다 사용자 인터페이스 \(UI\)입니다.  이 몇 가지 예제 시나리오에서 완성 되는  **감시** 창이 나 중단점 속성 창의 조건 필드에서.  
  
### 인터페이스 구현  
  
#### IVsIntellisenseHost  
 IntelliSense 팝업 창을 호스팅하는 UI 구성 요소를 지원 해야를 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 인터페이스입니다.  기본 코어 편집기의 텍스트 보기 주식을 포함 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 인터페이스 구현 현재 IntelliSense 기능을 유지할 수 있습니다.  대부분의 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 나타냅니다 어떤 부분에서 구현 된 인터페이스의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 인터페이스입니다.  IntelliSense UI 처리, 캐럿 및 선택 영역 조작 및 간단한 텍스트 대체 기능 하위 집합을 포함합니다.  뿐만 아니라, 해당 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 인터페이스 있습니다 별도 IntelliSense "제목" 및 "컨텍스트" 컨텍스트에 대해 사용 되는 텍스트 버퍼에 직접 존재 하지 않는 주제에 대 한 IntelliSense를 제공할 수 있도록 합니다.  
  
#### IVsIntellisenseHost.GetHostFlags  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 인터페이스 공급자가 구현 해야 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetHostFlags%2A> IntelliSense 어떤 유형의 호스트 기능을 확인 하는 클라이언트를 사용 하는 메서드를 지원 합니다.  
  
 호스트에 정의 된 플래그, [IntelliSenseHostFlags](../extensibility/intellisensehostflags.md)를 아래에 요약 되어 있습니다.  
  
|IntelliSense 호스트 플래그|설명|  
|--------------------------|--------|  
|IHF\_READONLYCONTEXT|컨텍스트 버퍼에는이 플래그가 의미 읽기 전용 및 편집 제목 텍스트 내 에서만 발생 합니다.|  
|IHF\_NOSEPERATESUBJECT|이 플래그는 방법이 설정 없음 별도 IntelliSense 주제입니다.  주체 컨텍스트 버퍼에 같은 전통에 있는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> IntelliSense 시스템입니다.|  
|IHF\_SINGLELINESUBJECT|제목 없는이 플래그가 설정 여러 줄, 한 줄 등의 편집은  **조사식** 창.|  
|IHF\_FORCECOMMITTOCONTEXT|이 플래그를 설정 하 고 상황에 맞는 버퍼를 업데이트 해야 하는 경우 호스트 컨텍스트 버퍼를 무시에 대 한 읽기 전용 플래그 및 계속 편집할 수 있습니다.|  
|IHF\_OVERTYPE|\(주제 또는 컨텍스트\) 편집 수행 합니다.|  
  
#### IVsIntellisenseHost.BeforeCompletorCommit 및 IVsIntellisenseHost.AfterCompletorCommit  
 이러한 콜백 메서드 텍스트 전처리 및 후 처리 수 있도록 노력 하 고 후 완료 창에 의해 호출 됩니다.  
  
#### IVsIntellisenseCompletor  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseCompletor> 인터페이스의 통합된 개발 환경 \(IDE\)에 의해 사용 되는 표준 완료 창이 co\-creatable 버전입니다.  모든 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 인터페이스 신속 하 게 구현할 수 있습니다 IntelliSense이 completor 인터페이스를 사용 하 여.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop>