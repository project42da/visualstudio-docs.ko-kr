---
title: "IDebugDocumentText::GetContextOfPosition | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentText.GetContextOfPosition
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugDocumentText::GetContextOfPosition"
ms.assetid: 86560853-d9b1-499a-a1b5-ea06aa1f1f5c
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentText::GetContextOfPosition
제공 된 문자 위치 범위에 해당 하는 문서 컨텍스트 개체를 만듭니다.  
  
## 구문  
  
```  
HRESULT GetContextOfPosition(  
   ULONG                    cCharacterPosition,  
   ULONG                    cNumChars,  
   IDebugDocumentContext**  ppsc  
);  
```  
  
#### 매개 변수  
 `cCharacterPosition`  
 \[in\] 위치 문자 범위의 위치를 시작 합니다.  
  
 `cNumChars`  
 \[in\] 범위에 있는 문자의 개수입니다.  
  
 `ppsc`  
 \[out\] 지정 된 문자 위치 범위에 해당 하는 문서 컨텍스트 개체입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 제공 된 문자 위치 범위에 해당 하는 문서 컨텍스트 개체를 만듭니다.  
  
## 참고 항목  
 [IDebugDocumentText 인터페이스](../../winscript/reference/idebugdocumenttext-interface.md)