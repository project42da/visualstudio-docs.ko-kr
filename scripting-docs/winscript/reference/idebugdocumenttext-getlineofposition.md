---
title: "IDebugDocumentText::GetLineOfPosition | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentText.GetLineOfPosition
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugDocumentText::GetLineOfPosition"
ms.assetid: fe8d4802-ea16-49ca-8973-89dcaf6c915b
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentText::GetLineOfPosition
줄 번호 및 해당 줄의 문자 오프셋에 지정 된 문자 위치를 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetLineOfPosition(  
   ULONG   cCharacterPosition,  
   ULONG*  pcLineNumber,  
   ULONG*  pcCharacterOffsetInLine  
);  
```  
  
#### 매개 변수  
 `cCharacterPosition`  
 \[in\] 위치 문자 범위의 위치를 시작 합니다.  
  
 `pcLineNumber`  
 \[out\] 줄 번호의 범위입니다.  
  
 `pcCharacterOffsetInLine`  
 \[in, out\] 범위 내의 줄의 문자 오프셋 `pcLineNumber`.  이 매개 변수가 `NULL`, 메서드가 값을 반환 하지 않습니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드가 지정 된 문자 위치에 줄 번호 및 해당 줄의 문자 오프셋을 반환 합니다.  
  
## 참고 항목  
 [IDebugDocumentText 인터페이스](../../winscript/reference/idebugdocumenttext-interface.md)