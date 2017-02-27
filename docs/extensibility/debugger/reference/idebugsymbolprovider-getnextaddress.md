---
title: "IDebugSymbolProvider::GetNextAddress | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugSymbolProvider::GetNextAddress"
helpviewer_keywords: 
  - "IDebugSymbolProvider::GetNextAddress 메서드"
ms.assetid: 704eeb94-cb13-49d1-82b6-7d83ed0f19c0
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugSymbolProvider::GetNextAddress
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

메서드는 지정 된 디버그 주소 뒤에 오는 디버그 주소를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetNextAddress(   
   IDebugAddress*  pAddress,  
   BOOL            fStatementOnly,  
   IDebugAddress** ppAddress  
);  
```  
  
```c#  
int GetNextAddress(   
   IDebugAddress     pAddress,  
   bool              fStatementOnly,  
   out IDebugAddress ppAddress  
);  
```  
  
#### 매개 변수  
 `pAddress`  
 \[in\] 디버그 주소를 지정 합니다.  
  
 `fStatementOnly`  
 \[in\] TRUE 이면 디버그 주소 단일 문으로 제한 됩니다.  
  
 `ppAddress`  
 \[out\] 다음 디버그 주소를 반환합니다.  
  
## 반환 값  
 올바른 반환 `HRESULT`, 일반적으로 S\_OK입니다.  
  
## 참고 항목  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)