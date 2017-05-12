---
title: "IJsDebugFrame::Evaluate 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugFrame.Evaluate
apilocation: jscript9diag.dll
ms.assetid: 0ee61340-37b8-4fbb-a028-748b5315e279
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugFrame::Evaluate 메서드
이 스택 프레임의 컨텍스트에서 식을 계산합니다.  
  
## 구문  
  
```  
HRESULT Evaluate(  
   LPCOLESTR pExpressionText,  
   IJsDebugProperty **ppDebugProperty,  
   BSTR *pError  
);  
```  
  
#### 매개 변수  
 `pExpressionText`  
 \[in\] 계산할 식입니다.  
  
 `ppDebugProperty`  
 \[out\] 속성 브라우저를 나타내는 개체입니다.  
  
 `pError`  
 \[out\] 오류가 발생한 경우의 오류 메시지입니다.  
  
## 반환 값  
  
## 설명  
 다음과 같은 정보를 반환: S\_OK: 평가 성공, \*ppDebugProperty는 평가 결과를 포함합니다.  S\_FALSE: 평가 오류를 throw합니다\(또는 평가 작업이 지원되지 않습니다\), \*pError는 오류 메시지를 포함합니다.  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugFrame 인터페이스](../../winscript/reference/ijsdebugframe-interface.md)