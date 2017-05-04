---
title: "IJsDebugBreakPoint::GetDocumentPosition 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJSDebugBreakPoint.GetDocumentPosition
apilocation: jscript9diag.dll
ms.assetid: 886df8ba-a59a-48a7-87f2-3b669e71528f
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugBreakPoint::GetDocumentPosition 메서드
중단점이 바인딩된 문의 위치를 반환합니다.  
  
## 구문  
  
```  
HRESULT GetDocumentPosition(  
   UINT64 *pDocumentId,  
   DWORD *pCharacterOffset,  
   DWORD *pStatementCharCount  
);  
```  
  
#### 매개 변수  
 `pDocumentId`  
 \[out\] 소스 문서의 고유 ID\(IDebugDocumentText에 대한 포인터\)입니다.  
  
 `pCharacterOffset`  
 \[out\] 스크립트의 시작 부분에서 0부터 시작하는 문자 오프셋입니다.  
  
 `pStatementCharCount`  
 \[out\] \*pCharacterOffset에서 시작하는 현재 문의 길이\(문자 수\)입니다.  
  
## 반환 값  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugBreakPoint 인터페이스](../../winscript/reference/ijsdebugbreakpoint-interface.md)