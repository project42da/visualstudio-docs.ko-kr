---
title: "IDebugDocumentHelper::SetDebugDocumentHost | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentHelper.SetDebugDocumentHost
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugDocumentHelper::SetDebugDocumentHost"
ms.assetid: b26a03c3-8a3f-47b0-b916-4c65d5500f10
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentHelper::SetDebugDocumentHost
집합의 `IDebugDocumentHost` 이 문서에 대 한.  
  
## 구문  
  
```  
HRESULT SetDebugDocumentHost(  
   IDebugDocumentHost*  pddh  
);  
```  
  
#### 매개 변수  
 `pddh`  
 \[in\] 디버그 문서 호스트입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 `IDebugDocumentHost` 인터페이스 사용에 대 한 스마트 호스트 구문 색상 표시, 문서에서 컨텍스트 지연 된 텍스트를 가져오고 새로 생성 제어 개체를 반환 합니다.  
  
## 참고 항목  
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [IDebugDocumentHost 인터페이스](../../winscript/reference/idebugdocumenthost-interface.md)