---
title: "IDebugProperty3 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProperty3"
helpviewer_keywords: 
  - "IDebugProperty3 인터페이스"
ms.assetid: 8f9be68d-4490-4eca-8f6b-8a10ed77e226
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugProperty3
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스에 대 한 지원을 제공합니다.  
  
-   속성에 연결 되는 임의 길이의 문자열을 검색 합니다.  
  
-   속성을 연결 하는 고유 ID입니다.  
  
-   이 속성에 대 한 사용자 지정 보기 권한자 목록 검색.  
  
-   모든 결과 오류를 보고 하는 기능을 속성의 값을 설정 합니다.  
  
## 구문  
  
```  
IDebugProperty3 : IDebugProperty2  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\)를 구현 하는 동일한 개체에서이 인터페이스는 구현 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 긴 문자열, 속성 Id 및 사용자 지정 뷰어를 지원 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 있는 `IDebugProperty2` 이 인터페이스를 가져올 수 있는 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 `IDebugProperty2`에서 상속되는 메서드 외에 `IDebugProperty3` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetStringCharLength](../../../extensibility/debugger/reference/idebugproperty3-getstringcharlength.md)|속성에 연결 문자열의 길이 반환 합니다.|  
|[GetStringChars](../../../extensibility/debugger/reference/idebugproperty3-getstringchars.md)|사용자가 제공한 버퍼의 문자열을 반환합니다.|  
|[CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)|이 속성에 대 한 고유 ID를 만듭니다.|  
|[DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md)|이 속성에 대 한 고유 ID를 소멸 시킵니다.|  
|[GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md)|이 속성을 볼 수 있는 사용자 지정 사용자의 수를 반환 합니다.|  
|[GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)|이 속성을 볼 수 있는 사용자 지정 사용자 목록을 반환 합니다.|  
|[SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md)|면 오류 메시지를 반환 하는이 속성의 값을 설정 합니다.|  
  
## 설명  
 [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md)속성 값을 설정 합니다 \(SDM\)에 대 한 세션 디버그 관리자입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)