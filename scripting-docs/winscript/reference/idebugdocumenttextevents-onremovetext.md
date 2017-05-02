---
title: "IDebugDocumentTextEvents::onRemoveText | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentTextEvents.onRemoveText
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDebugDocumentTextEvents::onRemoveText"
ms.assetid: c5dfe674-c42f-4e57-9d48-8380d5aa206b
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentTextEvents::onRemoveText
텍스트 문서에서 제거 되었음을 나타냅니다.  
  
## 구문  
  
```  
HRESULT onRemoveText(  
   ULONG  cCharacterPosition,  
   ULONG  cNumToRemove  
);  
```  
  
#### 매개 변수  
 `cCharacterPosition`  
 \[in\] 첫 번째 문자의 문자 위치를 제거 합니다.  
  
 `cNumToRemove`  
 \[in\] 문자를 제거 합니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 텍스트 문서에서 제거 되었음을 나타냅니다.  
  
## 참고 항목  
 [IDebugDocumentTextEvents 인터페이스](../../winscript/reference/idebugdocumenttextevents-interface.md)   
 [IDebugDocumentTextEvents::onInsertText](../../winscript/reference/idebugdocumenttextevents-oninserttext.md)