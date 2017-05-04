---
title: "IDebugDocumentTextAuthor::ReplaceText | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentTextAuthor.ReplaceText
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDebugDocumentTextAuthor::ReplaceText"
ms.assetid: f89304e6-5be0-45a5-947d-2c59c3c0a05e
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentTextAuthor::ReplaceText
문서에서 텍스트를 바꿉니다.  
  
## 구문  
  
```  
HRESULT ReplaceText(  
   ULONG    cCharacterPosition,  
   ULONG    cNumToReplace,  
   OLECHAR  pcharText[]  
);  
```  
  
#### 매개 변수  
 `cCharacterPosition`  
 \[in\] 대체 문자 범위의 위치를 시작 합니다.  
  
 `cNumToReplace`  
 \[in\] 바꿀 문자의 개수입니다.  
  
 `pcharText[]`  
 \[in\] 이전 문자를 바꾸려면 새 문자를 포함 하는 버퍼입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 문서에서에서 텍스트를 바꿉니다.  
  
## 참고 항목  
 [IDebugDocumentTextAuthor 인터페이스](../../winscript/reference/idebugdocumenttextauthor-interface.md)