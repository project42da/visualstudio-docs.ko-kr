---
title: "IDebugPortPicker | Microsoft Docs"
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
  - "IDebugPortPicker 인터페이스"
ms.assetid: 8b7f6685-a3c5-4355-b706-c1b574f6ff84
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugPortPicker
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

포트 선택에 대 한 사용자 지정 된 UI를 나타냅니다.  
  
## 구문  
  
```  
IDebugPortPicker : IUnknown  
```  
  
## 구현자 참고 사항  
 포트 공급자가이 인터페이스를 구현 합니다.  CLSID로 노출 하 고 가리키는 포트 공급자가 포트 선택을 정의 `metricPortPickerCLSID` 미터에 노출 된 CLSID입니다.  
  
## 메서드  
 다음 표에서 메서드를 `IDebugPortPicker`.  
  
|메서드|설명|  
|---------|--------|  
|[DisplayPortPicker](../../../extensibility/debugger/reference/idebugportpicker-displayportpicker.md)|포트를 선택할 수 있도록 하는 지정 된 대화 상자를 표시 합니다.|  
|[SetSite](../../../extensibility/debugger/reference/idebugportpicker-setsite.md)|서비스 공급자를 설정합니다.|  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll