---
title: "IDebugCoreServer3::DiagnoseWebDebuggingError | Microsoft Docs"
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
  - "IDebugCoreServer3::DiagnoseWebDebuggingError"
helpviewer_keywords: 
  - "IDebugCoreServer3::DiagnoseWebDebuggingError"
ms.assetid: 8c4570ca-ae55-42f2-bbaa-8d8e75d2fa19
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugCoreServer3::DiagnoseWebDebuggingError
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

Auto\-attach는 이유를 확인 하려는 시도 실패 했습니다.  
  
## 구문  
  
```cpp#  
HRESULT DiagnoseWebDebuggingError(  
   LPCWSTR pszUrl  
);  
```  
  
```c#  
int DiagnoseWebDebuggingError(  
   string pszUrl  
);  
```  
  
#### 매개 변수  
 `pszUrl`  
 \[in\] 현재 사용 되는. 항상 null 값으로 설정 해야 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  다른 일반적인 반환 코드는 다음과 같습니다.  
  
|코드|설명|  
|--------|--------|  
|`S_WEBDBG_UNABLE_TO_DIAGNOSE`|원격 서버 디버깅 시작 실패 이유를 확인할 수 없습니다.|  
|`S_WEBDBG_DEBUG_VERB_BLOCKED`|권한이 부족 하기 때문에 원격 서버를 디버깅할 수 없습니다 또는 DEBUG 동사를 사용할 수 있기 때문에.|  
|`E_WEBDBG_DEBUG_VERB_BLOCKED`|웹 서버가 잠겨 있기 때문 및 디버깅을 활성화 하는 데 필요한 DEBUG 동사를 차단 하 고 있습니다.|  
  
## 참고 항목  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)