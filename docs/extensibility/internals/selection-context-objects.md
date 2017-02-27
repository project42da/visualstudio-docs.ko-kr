---
title: "컨텍스트 개체 선택 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "선택 항목을 추적"
  - "컨텍스트 개체 선택"
ms.assetid: 7308ea8f-a42c-47e5-954e-7dee933dce7a
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# 컨텍스트 개체 선택
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\) 전역 선택 컨텍스트 개체를 사용 하 여 IDE에 표시 되어야 할 작업을 결정 합니다.  각 창에는 IDE에서에서 전역 선택 컨텍스트에 푸시된 자체 선택 영역 컨텍스트 개체를 사용할 수 있습니다.  해당 창에 포커스가 있을 때 IDE 전역 선택 컨텍스트 창에서 값이 업데이트 됩니다.  자세한 내용은 [사용자에 게 피드백](../../extensibility/internals/feedback-to-the-user.md)를 참조하십시오.  
  
 각 창 프레임 또는 IDE에서 사이트 라는 서비스가 <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection>.  창 프레임에 배치 됩니다 사용자 Vspackage에서 만든 개체를 호출 해야 해당 `QueryService` 메서드에 대 한 포인터를 얻을 수는 <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection> 인터페이스.  
  
 프레임 창의 일부는 시작 될 때 전역 선택 영역 컨텍스트를 전파 하는에서 해당 선택 영역 컨텍스트 정보를 유지할 수 있습니다.  이 기능은 빈 선택 영역을 시작 해야 하는 도구 창에 대 한 유용 합니다.  
  
 Vspackages를 모니터링할 수 있는 전역 선택 상황에 맞는 트리거 이벤트를 수정 합니다.  VSPackages 수행할 수 다음 작업을 구현 하 여 `IVsTrackSelectionEx` 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection> 인터페이스:  
  
-   계층 구조에서 현재 사용 중인 파일을 업데이트 합니다.  
  
-   특정 형식의 요소에 대 한 변경 내용을 모니터링 합니다.  특수 Vspackage를 사용 하는 경우 예를 들어,  **속성** 창에서 활성 변경 내용을 모니터링할 수 있습니다  **속성** 창 당신 필요할 때 다시 시작 합니다.  
  
 다음 순서 대로 추적 선택의 일반적인 과정을 보여 줍니다.  
  
1.  IDE에서 새로 연된 창의 선택 영역 컨텍스트를 검색 및 글로벌 선택 영역 컨텍스트를 전환 합니다.  선택 영역 컨텍스트를 HIERARCHY\_DONTPROPAGATE 또는 SELCONTAINER\_DONTPROPAGATE 사용 하는 경우 해당 정보는 글로벌 컨텍스트로 전파 되지 않습니다.  자세한 내용은 [사용자에 게 피드백](../../extensibility/internals/feedback-to-the-user.md)를 참조하십시오.  
  
2.  이 요청한 모든 Vspackage는 알림 이벤트를 브로드캐스팅합니다.  
  
3.  있는 Vspackage를 도구, 또는 기타 유사한 작업을 다시 활성화 하는 계층 구조를 업데이트 하는 등의 작업을 수행 하 여 수신 하는 이벤트 역할을 합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>   
 [Visual Studio에서 계층 구조](../../extensibility/internals/hierarchies-in-visual-studio.md)   
 [선택 및 IDE에서 통화](../../extensibility/internals/selection-and-currency-in-the-ide.md)   
 [프로젝트 형식](../../extensibility/internals/project-types.md)