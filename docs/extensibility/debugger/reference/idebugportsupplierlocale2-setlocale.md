---
title: "IDebugPortSupplierLocale2::SetLocale | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugPortSupplierLocale2::SetLocale"
ms.assetid: 21e88510-caac-405e-ba45-cb00e19a28bc
caps.latest.revision: 5
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 5
---
# IDebugPortSupplierLocale2::SetLocale
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

포트 공급자에 대 한 로케일을 설정합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetLocale(  
   WORD wLangID  
);  
```  
  
```c#  
int SetLocale(  
   ushort wLangID  
);  
```  
  
#### 매개 변수  
 `wLangID`  
 설정 하려면 로케일 식별자입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugPortSupplierLocale2](../../../extensibility/debugger/reference/idebugportsupplierlocale2.md)