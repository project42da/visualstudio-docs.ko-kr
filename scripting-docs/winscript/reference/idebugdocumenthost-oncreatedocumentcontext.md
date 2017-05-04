---
title: "IDebugDocumentHost::OnCreateDocumentContext | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentHost.OnCreateDocumentContext
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDebugDocumentHost::OnCreateDocumentContext"
ms.assetid: 080c8604-cfd7-484e-a337-15040870e683
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentHost::OnCreateDocumentContext
호스트는 새 문서 컨텍스트 작성 되 고 호스트에서 선택적으로 새 컨텍스트를 알 수 없는 제어를 반환할 수 알립니다.  
  
## 구문  
  
```  
HRESULT OnCreateDocumentContext(  
   IUnknown**  ppunkOuter  
);  
```  
  
#### 매개 변수  
 `ppunkOuter`  
 \[out\] 새 컨텍스트를 제어 하는 개체입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|호스트 제어 하는 개체를 제공 하지 않습니다.|  
  
## 설명  
 이 메서드는 호스트를 도우미에서 제공 하는 문서의 컨텍스트에 새 기능을 추가할 수 있습니다.  이 메서드는 반환  **E\_NOTIMPL** 또는 경우 호출자는 컨텍스트를 만드는 null 외부 개체입니다.  
  
## 참고 항목  
 [IDebugDocumentHost 인터페이스](../../winscript/reference/idebugdocumenthost-interface.md)