---
title: "IDebugDocumentHost 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugDocumentHost 인터페이스"
ms.assetid: 2fed4220-b6a2-47c6-bf28-daad7dd5c42d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentHost 인터페이스
구문 색, 디버거를 호스트 관련 기능을 노출 합니다.  `IDebugDocumentHelper::SetDebugDocumentHost` 메서드는이 인터페이스에 대 한 인수로 사용 합니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugDocumentHost` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugDocumentHost::GetDeferredText](../../winscript/reference/idebugdocumenthost-getdeferredtext.md)|사용 하 여 추가 된 문자의 범위를 반환 합니다. `IDebugDocumentHelper::AddDeferredText`, 원래 호스트 문서에서.|  
|[IDebugDocumentHost::GetScriptTextAttributes](../../winscript/reference/idebugdocumenthost-getscripttextattributes.md)|문서의 텍스트 블록에 대 한 텍스트 특성을 반환합니다.|  
|[IDebugDocumentHost::OnCreateDocumentContext](../../winscript/reference/idebugdocumenthost-oncreatedocumentcontext.md)|호스트는 새 문서 컨텍스트 작성 되 고 호스트에서 선택적으로 새 컨텍스트를 제어 하는 개체를 반환할 수 알립니다.|  
|[IDebugDocumentHost::GetPathName](../../winscript/reference/idebugdocumenthost-getpathname.md)|문서의 소스 파일의 전체 경로 \(파일 이름 포함\)를 반환 합니다.|  
|[IDebugDocumentHost::GetFileName](../../winscript/reference/idebugdocumenthost-getfilename.md)|경로 정보 없이 문서의 이름을 반환합니다.|  
|[IDebugDocumentHost::NotifyChanged](../../winscript/reference/idebugdocumenthost-notifychanged.md)|호스트 문서의 원본 파일이 저장 된 내용을 고쳐야 할 알려줍니다.|