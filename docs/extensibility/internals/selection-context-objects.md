---
title: 컨텍스트 개체 선택 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- selection, tracking
- selection, context objects
ms.assetid: 7308ea8f-a42c-47e5-954e-7dee933dce7a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 04ccc4a57ac7af144c134761119433b7533e9bec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="selection-context-objects"></a>컨텍스트 개체 선택
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE) 전역 선택 컨텍스트 개체를 사용 하 여 IDE에서 표시 되어야 할 사항을 결정 합니다. IDE의 각 창 글로벌 선택 항목 컨텍스트를 푸시할 자체 선택 컨텍스트 개체를 가질 수 있습니다. IDE는 해당 창에 포커스가 있을 때 창에서 값을 가진 전역 선택 항목 컨텍스트를 업데이트 합니다. 자세한 내용은 참조 [사용자에 게 피드백](../../extensibility/internals/feedback-to-the-user.md)합니다.  
  
 각 창 프레임 또는 IDE에서 사이트에 라는 서비스 <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection>합니다. 창 프레임에 배치 하는 VSPackage에서 만든 개체를 호출 해야 합니다는 `QueryService` 에 포인터를 얻으려면 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection> 인터페이스입니다.  
  
 프레임 창 부분이 시작 될 때 전역 선택 항목 컨텍스트를 전파 되는 선택 컨텍스트 정보를 유지할 수 있습니다. 이 기능은 선택 영역이로 시작 해야 할 수 있는 도구 창에 유용 합니다.  
  
 Vspackage를 모니터링할 수 있는 전역 선택 컨텍스트 트리거 이벤트를 수정 합니다. Vspackage를 구현 하 여 다음 작업을 수행할 수 `IVsTrackSelectionEx` 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection> 인터페이스:  
  
-   계층 구조에서 현재 활성 파일을 업데이트 합니다.  
  
-   특정 유형의 요소에 변경 내용을 모니터링 합니다. 예를 들어 VSPackage는 특수 한을 사용 하는 경우 **속성** 창 활성에서 변경 내용을 모니터링할 수 있습니다 **속성** 창 고 필요할 때 원하는 대로 다시 시작 합니다.  
  
 다음 순서 대로 선택 영역 추적 일반적인 과정을 보여 줍니다.  
  
1.  IDE 새로 열린된 창에서 선택 항목 컨텍스트를 검색 하 고 글로벌 선택 항목 컨텍스트에 배치 합니다. 선택 항목 컨텍스트 모드를 사용할지 HIERARCHY_DONTPROPAGATE SELCONTAINER_DONTPROPAGATE, 해당 정보는 전역 컨텍스트를 전파 되지 않습니다. 자세한 내용은 참조 [사용자에 게 피드백](../../extensibility/internals/feedback-to-the-user.md)합니다.  
  
2.  알림 이벤트를 요청한 모든 VSPackage로 브로드캐스팅 되며.  
  
3.  VSPackage는 도구 또는 기타 유사한 작업을 다시 활성화 하는 계층 업데이트와 같은 작업을 수행 하 여 받은 이벤트에 작업을 수행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>   
 [Visual Studio에서 계층 구조](../../extensibility/internals/hierarchies-in-visual-studio.md)   
 [선택 및 IDE에서 통화](../../extensibility/internals/selection-and-currency-in-the-ide.md)   
 [프로젝트 형식](../../extensibility/internals/project-types.md)