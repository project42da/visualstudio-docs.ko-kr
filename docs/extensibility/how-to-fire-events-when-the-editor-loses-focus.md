---
title: "방법: 편집기 포커스를 잃을 때 이벤트를 발생 시킬 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - fire events on losing focus
ms.assetid: 64d40695-6917-468a-8037-a253453ac159
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: bb20adf3950e87c37e2ca64bcd78913839f89d01
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-fire-events-when-the-editor-loses-focus"></a>방법: 편집기 포커스를 잃을 때 이벤트 발생
경우에 따라 편집기 창 프레임에 포커스를 잃을 때 확인 해야 합니다. 예를 들어 편집기에 포커스를 잃을 후 코드 창에서 코드를 추출 해야 합니다. 다음 절차는 포커스를 잃을 편집기에 대 한 알림을 수신 하는 단계를 제공 합니다.  
  
### <a name="to-fire-an-event-in-response-to-an-editor-losing-focus"></a>포커스를 잃을 편집기에 대 한 응답에서 이벤트를 실행 하려면  
  
1.  확보 하 여 선택 영역 이벤트를 모니터링 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection> 에서 개체 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>합니다.  
  
2.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.AdviseSelectionEvents%2A> 제공 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents> 개체입니다.  
  
3.  에 대 한 호출에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A>를 찾도록 `elementid==SEID_WindowFrame`합니다.  
  
4.  테스트는 `varValueNew` 두 가지 작업에 대 한 매개 변수:  
  
    1.  원하는 창 프레임입니다.  
  
    2.  프로그램 손실 해당 창 프레임을 선택 하는 점입니다.