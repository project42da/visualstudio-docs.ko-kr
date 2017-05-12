---
title: "IDebugStackFrame::GetDescriptionString | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugStackFrame.GetDescriptionString
apilocation: jscript.dll
helpviewer_keywords: 
  - "IDebugStackFrame::GetDescriptionString"
ms.assetid: a2ddc069-c440-4dee-98dc-ab7c78773b94
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugStackFrame::GetDescriptionString
스택 프레임의 짧은 또는 긴 텍스트 설명을 반환합니다.  
  
## 구문  
  
```  
HRESULT GetDescriptionString(  
   BOOL   fLong,  
   BSTR*  pbstrDescription  
);  
```  
  
#### 매개 변수  
 `fLong`  
 \[in\] 플래그를 위치 `TRUE` 긴 설명을 반환 하 고 `FALSE` 간단한 설명을 반환 합니다.  
  
 `pbstrDescription`  
 \[out\] 스택 프레임의 설명입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 일반적으로 경우 `fLong` 는 `FALSE`, 스택 프레임과 연관 된 함수 이름만이 메서드를 제공 합니다.  때 `fLong` 는 `TRUE`에서이 메서드는 함수 매개 변수 및 기타 관련 정보 또한 제공할 수 있습니다.  
  
## 참고 항목  
 [IDebugStackFrame 인터페이스](../../winscript/reference/idebugstackframe-interface.md)