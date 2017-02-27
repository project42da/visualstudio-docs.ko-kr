---
title: "IDebugSettingsCallback2::GetMetricString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugSettingsCallback2::GetMetricString"
  - "GetMetricString"
ms.assetid: ecc875a2-8ac6-444c-a839-5191a780fd6b
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugSettingsCallback2::GetMetricString
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

지정 된 이름 메트릭 값 문자열을 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetMetricString(  
    LPCWSTR pszType,  
    REFGUID guidSection,  
    LPCWSTR pszMetric,  
    BSTR*   pbstrValue  
);  
```  
  
```c#  
private int GetMetricString(  
    string     pszType,  
    ref Guid   guidSection,  
    string     pszMetric,  
    out string pbstrValue  
);  
```  
  
#### 매개 변수  
 `pszType`  
 \[in\] 메트릭 형식입니다.  
  
 `guidSection`  
 \[in\] 섹션의 고유 식별자입니다.  
  
 `pszMetric`  
 \[in\] 메트릭의 이름입니다.  
  
 `pbstrValue`  
 \[out\] 메트릭 값 문자열을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)