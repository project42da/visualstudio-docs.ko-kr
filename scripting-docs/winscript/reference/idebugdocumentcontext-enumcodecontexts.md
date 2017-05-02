---
title: "IDebugDocumentContext::EnumCodeContexts | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentContext.EnumCodeContexts
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugDocumentContext::EnumCodeContexts"
ms.assetid: fb0aa64e-c458-4ef1-bcd8-5cebdc972549
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentContext::EnumCodeContexts
이 문서 컨텍스트와 연관 된 코드 컨텍스트를 열거 합니다.  
  
## 구문  
  
```  
HRESULT EnumCodeContexts(  
   IEnumDebugCodeContexts**  ppescc  
);  
```  
  
#### 매개 변수  
 `ppescc`  
 \[out\] 이 문서 컨텍스트와 연관 된 코드 컨텍스트입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 문서 서식 파일 또는 include 파일 문서 일반적으로 하나의 코드 컨텍스트와 관련입니다.  
  
## 참고 항목  
 [IDebugDocumentContext 인터페이스](../../winscript/reference/idebugdocumentcontext-interface.md)