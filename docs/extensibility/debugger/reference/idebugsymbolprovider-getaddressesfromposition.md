---
title: "IDebugSymbolProvider::GetAddressesFromPosition | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugSymbolProvider::GetAddressesFromPosition"
helpviewer_keywords: 
  - "IDebugSymbolProvider::GetAddressesFromPosition 메서드"
ms.assetid: 1b0f02cb-8ace-4614-88f3-0e10239012b3
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugSymbolProvider::GetAddressesFromPosition
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 문서 위치를에 배열 디버그 주소를 매핑합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetAddressesFromPosition(   
   IDebugDocumentPosition2* pDocPos,  
   BOOL                     fStatmentOnly,  
   IEnumDebugAddresses**    ppEnumBegAddresses,  
   IEnumDebugAddresses**    ppEnumEndAddresses  
);  
```  
  
```c#  
int GetAddressesFromPosition(   
   IDebugDocumentPosition2  pDocPos,  
   bool                     fStatmentOnly,  
   out IEnumDebugAddresses  ppEnumBegAddresses,  
   out IEnumDebugAddresses  ppEnumEndAddresses  
);  
```  
  
#### 매개 변수  
 `pDocPos`  
 \[in\] 문서 위치입니다.  
  
 `fStatmentOnly`  
 \[in\] TRUE 이면 디버그 주소 단일 문으로 제한 됩니다.  
  
 `ppEnumBegAddresses`  
 \[out\] 이 문 또는 줄에 연결 된 디버그 시작 주소에 대 한 열거자를 반환 합니다.  
  
 `ppEnumEndAddresses`  
 \[out\] 반환 된 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) 이 문이나 줄 관련 된 끝 디버그 주소에 대 한 열거자입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 문서 위치 일반적으로 다양 한 소스 줄을 나타냅니다.  끝 디버그 주소 이러한 선과 연결 및 시작 하는이 메서드를 제공 합니다.  일부 언어는 문이 두 개 이상 포함 하는 줄 이나 여러 줄에 걸쳐 문이 있습니다.  이 방법을 디버그 주소 단일 문으로 제한 하는 플래그를 제공 합니다.  
  
 단일 문을 템플릿의 경우 디버그 주소가 여러 개 있을 수 있습니다.  
  
## 참고 항목  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md)   
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)