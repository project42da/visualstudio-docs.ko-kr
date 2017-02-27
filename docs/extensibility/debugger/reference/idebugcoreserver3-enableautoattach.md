---
title: "IDebugCoreServer3::EnableAutoAttach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugCoreServer3::EnableAutoAttach"
helpviewer_keywords: 
  - "IDebugCoreServer3::EnableAutoAttach"
ms.assetid: 06aa633b-263b-4e08-8844-9a52d5120b94
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugCoreServer3::EnableAutoAttach
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

자동 지정 된 디버깅 엔진에 첨부할 수 있습니다.  
  
## 구문  
  
```cpp#  
HRESULT EnableAutoAttach(  
   GUID*     rgguidSpecificEngines,  
   DWORD     celtSpecificEngines,  
   LPCOLESTR pszStartPageUrl,  
   BSTR*     pbstrSessionId  
);  
```  
  
```c#  
int EnableAutoAttach(  
   Guid[]     rgguidSpecificEngines,  
   uint       celtSpecificEngines,  
   string     pszStartPageUrl,  
   out string pbstrSessionId  
);  
```  
  
#### 매개 변수  
 `rgguidSpecificEngines`  
 \[in\] 자동 연결로 표시를 각 디버그 엔진에 대 한 Guid의 배열입니다.  
  
 `celtSpecificEngines`  
 \[in\] 엔진에서 지정 된 수를 `rgguidSpecificEngines`.  
  
 `pszStartPageUrl`  
 \[in\] 자동 연결 사용 시작 URL입니다.  
  
 `pbstrSessionID`  
 \[out\] 자동 연결 된 세션의 ID입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  한 가지 오류 코드는 `E_AUTO_ATTACH_NOT_REGISTERED`, 나타내는 auto\-attach 클래스 팩토리가 등록 되지 않았습니다.  
  
## 설명  
 지정 된 URL과 연결 된 프로그램을 시작 하는 경우 지정 된 디버깅 엔진 자동으로 시작 되 고 연결 됩니다.  
  
## 참고 항목  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)