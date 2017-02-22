---
title: "IDebugSymbolProvider::GetAddressesFromContext | Microsoft Docs"
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
  - "IDebugSymbolProvider::GetAddressesFromContext"
helpviewer_keywords: 
  - "IDebugSymbolProvider::GetAddressesFromContext 메서드"
ms.assetid: a3124883-a255-4543-a5ec-e1c7a97beb69
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugSymbolProvider::GetAddressesFromContext
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 문서의 컨텍스트에 디버그 주소 배열에 매핑합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetAddressesFromContext(   
   IDebugDocumentContext2* pDocContext,  
   BOOL                    fStatmentOnly,  
   IEnumDebugAddresses**   ppEnumBegAddresses,  
   IEnumDebugAddresses**   ppEnumEndAddresses  
);  
```  
  
```c#  
int GetAddressesFromContext(  
   IDebugDocumentContext2  pDocContext,  
   bool                    fStatmentOnly,  
   out IEnumDebugAddresses ppEnumBegAddresses,  
   out IEnumDebugAddresses ppEnumEndAddresses  
);  
```  
  
#### 매개 변수  
 `pDocContext`  
 \[in\] 문서 컨텍스트입니다.  
  
 `fStatmentOnly`  
 \[in\] TRUE 이면 디버그 주소 단일 문으로 제한 됩니다.  
  
 `ppEnumBegAddresses`  
 \[out\] 이 문 또는 줄에 연결 된 디버그 시작 주소에 대 한 열거자를 반환 합니다.  
  
 `ppEnumEndAddresses`  
 \[out\] 반환 된 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) 이 문이나 줄 관련 된 끝 디버그 주소에 대 한 열거자입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 문서 컨텍스트 일반적으로 다양 한 소스 줄을 나타냅니다.  끝 디버그 주소 이러한 선과 연결 및 시작 하는이 메서드를 제공 합니다.  일부 언어는 문이 두 개 이상 포함 하는 줄 이나 여러 줄에 걸쳐 문이 있습니다.  이 방법을 디버그 주소 단일 문으로 제한 하는 플래그를 제공 합니다.  
  
 단일 문을 템플릿의 경우 디버그 주소가 여러 개 있을 수 있습니다.  
  
## 참고 항목  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)   
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)