---
title: "속성 창 선택 영역 추적 발표 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기[Visual Studio SDK], 속성 페이지 지원"
  - "속성 페이지, 선택 영역 추적"
  - "속성 창, 선택 영역 추적"
  - "선택 영역, 추적"
  - "편집기[Visual Studio SDK], 속성 창 지원"
ms.assetid: a7536f82-afd7-4894-9a60-84307fb92b7e
caps.latest.revision: 13
caps.handback.revision: 13
manager: "douge"
---
# 속성 창 선택 영역 추적 발표
작업 하는 경우는  **속성** 창 나를  **속성이** 폼, 텍스트 또는 선택 적용할 등록 정보를 보려면 선택 영역을 조정 하는 방법의 잘 알고 있어야 하 고 예를 들어, 페이지.  예를 들어, 단일 선택과 다중 선택 했는지 알아야 합니다.  IDE를 사용 하 여 선택 유형 \(단일 또는 여러 개\)를 알릴 필요가 있는 <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection> 인터페이스입니다.  이 인터페이스에 필요한 정보를 제공의  **속성이** 창입니다.  
  
### 선택 영역 환경에 알릴 수  
  
1.  Call `QueryInterface` for <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>.  
  
    1.  이렇게 하려면 보기를 만들 때 전달 사이트 포인터를 사용 합니다.  
  
    2.  호출 `QueryService` 보기에서는 `SID_STrackSelection` 서비스 합니다.  
  
         이에 대 한 포인터를 반환 합니다. <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection>.  
  
2.  호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> 선택이 변경 될 때마다 메서드 및 패스에 대 한 포인터를 구현 하는 개체에 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>.  
  
     선택 컨테이너 개체 단일 또는 다중 선택을 사용할 수 있으며 선택 정보에 포함 되어 있는 `IDispatch` 개체입니다.  호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> 메서드에 알립니다의  **속성** 선택 영역이 변경 된 창입니다.  **속성이** 창의 다음 사용 하 여 개체에 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 실제 객체 선택 및 단일 선택과 다중 선택 발생 여부를 결정 합니다.  
  
     여러 선택 영역을 지정 하는 경우 다음을  **속성** 창 개체에 대 한 공용 속성 사이의 교차 부분을 찾습니다.  단일 개체 선택 영역을 지정 하는 경우 다음의  **속성** 창 모든 개체에 대 한 속성을 표시 합니다.  
  
## 참고 항목  
 [속성 확장](../extensibility/internals/extending-properties.md)   
 [속성 페이지](../extensibility/internals/property-pages.md)