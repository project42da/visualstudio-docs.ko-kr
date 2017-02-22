---
title: "IDebugModule2::ReloadSymbols_Deprecated | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugModule2::ReloadSymbols"
helpviewer_keywords: 
  - "IDebugModule2::ReloadSymbols 메서드"
ms.assetid: 0f9f0133-7d58-4cd9-a6ca-1141e095749d
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugModule2::ReloadSymbols_Deprecated
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용 되지 않음.  사용 하지 않습니다.  이 모듈에 대 한 기호를 다시 로드합니다.  
  
## 구문  
  
```cpp#  
HRESULT ReloadSymbols(   
   LPCOLESTR pszUrlToSymbols,  
   BSTR*     pbstrDebugMessage  
);  
```  
  
```c#  
int ReloadSymbols(   
   string     pszUrlToSymbols,  
   out string pbstrDebugMessage  
);  
```  
  
#### 매개 변수  
 `pszUrlToSymbols`  
 \[in\] 기호 저장소의 경로입니다.  
  
 `pbstrDebugMessage`  
 \[out\] 모듈 창에서 모듈 이름 오른쪽에 표시 되는 상태 또는 오류 메시지와 같은 정보 메시지를 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  디버그 엔진을 항상 반환 해야 `E_FAIL`.  
  
## 설명  
 이 메서드는 더 이상 지원되지 않습니다.  구현에서 [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md) 메서드 대신 합니다.  
  
## 참고 항목  
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md)