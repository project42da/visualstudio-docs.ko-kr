---
title: "IJsDebugFrame::GetDocumentPositionWithName 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugFrame.GetDocumentPositionWithName
apilocation: jscript9diag.dll
ms.assetid: 1d994714-2c87-4a9e-ae14-a15eec9520c7
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugFrame::GetDocumentPositionWithName 메서드
사용자 수준 문서 내에서 이 스택 프레임의 현재 위치를 반환합니다.  
  
## 구문  
  
```  
HRESULT GetDocumentPositionWithName(  
   BSTR *pDocumentName,  
   DWORD *pLine,  
   DWORD *pColumn  
);  
```  
  
#### 매개 변수  
 `pDocumentName`  
 \[out\] 정적 스크립트의 경우 문서화할 URL입니다.  동적 스크립트의 경우 스크립트 형식이 포함된 이름\(예: eval 코드, 함수 코드 등\)이 반환됩니다.  
  
 `pLine`  
 \[out\] 문서 내에서 1부터 시작하는 줄 위치입니다.  
  
 `pColumn`  
 \[out\] 문서 내에서 1부터 시작하는 줄 위치입니다.  
  
## 반환 값  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugFrame 인터페이스](../../winscript/reference/ijsdebugframe-interface.md)