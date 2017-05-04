---
title: "IDebugStackFrame::GetLanguageString | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugStackFrame.GetLanguageString
apilocation: jscript.dll
helpviewer_keywords: 
  - "IDebugStackFrame::GetLanguageString"
ms.assetid: 561d6306-f214-422f-abc9-b502cbfbe208
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugStackFrame::GetLanguageString
언어의 짧은 또는 긴 텍스트 설명을 반환합니다.  
  
## 구문  
  
```  
HRESULT GetLanguageString(  
   BOOL   fLong,  
   BSTR*  pbstrLanguage  
);  
```  
  
#### 매개 변수  
 `fLong`  
 \[in\] 플래그를 위치 `TRUE` 긴 설명을 반환 하 고 `FALSE` 간단한 설명을 반환 합니다.  
  
 `pbstrLanguage`  
 \[out\] 설명 언어입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 일반적으로 경우 `fLong` 는 `FALSE`, 스택 프레임과 연결 된 언어 이름을이 메서드를 제공 합니다.  때 `fLong` 는 `TRUE`에서이 메서드는 전체 제품 설명을 제공할 수 있습니다.  
  
## 참고 항목  
 [IDebugStackFrame 인터페이스](../../winscript/reference/idebugstackframe-interface.md)