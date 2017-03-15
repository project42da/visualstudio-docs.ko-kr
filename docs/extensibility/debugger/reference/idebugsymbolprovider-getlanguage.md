---
title: "IDebugSymbolProvider::GetLanguage | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugSymbolProvider::GetLanguage"
helpviewer_keywords: 
  - "IDebugSymbolProvider::GetLanguage 메서드"
ms.assetid: e4142183-3d8b-418f-907f-4ee4c753d8ce
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugSymbolProvider::GetLanguage
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드 코드 디버그 주소에 사용 된 언어를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetLanguage(   
   IDebugAddress* pAddress,  
   GUID*          pguidLanguage,  
   GUID*          pguidLanguageVendor  
);  
```  
  
```c#  
int GetLanguage(  
   IDebugAddress pAddress,   
   out Guid      pguidLanguage,   
   out Guid      pguidLanguageVendor  
);  
```  
  
#### 매개 변수  
 `pAddress`  
 \[in\] Address 개체를 표시 하는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.  
  
 `pguidLanguage`  
 \[out\] 반환 된 `GUID` 는 언어를 지정 합니다.  
  
 `pguidLanguageVendor`  
 \[out\] 반환 된 `GUID` 해당 언어 공급 업체를 지정 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 디버그 엔진 올바른 식 계산기를 선택 하는 데 필요한 정보를 얻기 위해이 메서드를 호출 합니다.  
  
## 참고 항목  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)