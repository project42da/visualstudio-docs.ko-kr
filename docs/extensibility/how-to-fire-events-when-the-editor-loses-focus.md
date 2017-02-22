---
title: "방법: 편집기 포커스를 잃을 때 이벤트를 발생 시키고 | Microsoft Docs"
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
  - "편집기 [Visual Studio SDK] 레거시-포커스를 잃거나 이벤트를 발생 시킵니다."
ms.assetid: 64d40695-6917-468a-8037-a253453ac159
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: 편집기 포커스를 잃을 때 이벤트를 발생 시키고
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

편집기 창의 프레임으로 포커스를 넘겨줄 때 알아야 하는 경우가 있습니다.  예를 들어, 편집기에 더 이상 포커스가 없습니다 후 코드 창에서 코드를 추출 해야 합니다.  다음 절차는 편집기 포커스 손실의 알림을 수신 하는 단계를 제공 합니다.  
  
### 포커스를 잃을 편집기에 이벤트를 발생 시키려면  
  
1.  받아 선택 이벤트 모니터링은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection> 개체에서 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>.  
  
2.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.AdviseSelectionEvents%2A> 그리고이 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents> 개체입니다.  
  
3.  호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A>, 찾는 위치에 대 한 `elementid==SEID_WindowFrame`.  
  
4.  테스트는 `varValueNew` 매개 변수에 대 한 두 가지:  
  
    1.  찾고 있는 창 프레임입니다.  
  
    2.  지점에서 프로그램을 선택 하는 창 프레임 손실.