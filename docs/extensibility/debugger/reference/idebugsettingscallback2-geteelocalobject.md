---
title: "IDebugSettingsCallback2::GetEELocalObject | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugSettingsCallback2::GetEELocalObject"
ms.assetid: e69a3469-a049-420c-b918-c48a1e7b9baf
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugSettingsCallback2::GetEELocalObject
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

메트릭 이름 지정 식 계산기 로컬 개체를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetEELocalObject(  
   REFGUID     guidLang,  
   REFGUID     guidVendor,  
   LPCWSTR     pszMetric,  
   IUnknown ** ppUnk  
);  
```  
  
```c#  
private int GetEELocalObject(  
   ref Guid          guidLang,  
   ref Guid          guidVendor,  
   string            pszMetric,  
   out System.Object ppUnk  
);  
```  
  
#### 매개 변수  
 `guidLang`  
 \[in\] 프로그래밍 언어의 고유 식별자입니다.  
  
 `guidVendor`  
 \[in\] 공급 업체의 고유 식별자입니다.  
  
 `pszMetric`  
 \[in\] 메트릭의 이름입니다.  
  
 `ppUnk`  
 \[out\] 식이 반환 계산기 로컬 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)