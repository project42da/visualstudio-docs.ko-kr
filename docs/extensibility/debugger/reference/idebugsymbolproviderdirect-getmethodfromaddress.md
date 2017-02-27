---
title: "IDebugSymbolProviderDirect::GetMethodFromAddress | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugSymbolProviderDirect::GetMethodFromAddress"
  - "GetMethodFromAddress"
ms.assetid: 33ffd197-1221-41bc-a9f6-f133ebdcb783
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugSymbolProviderDirect::GetMethodFromAddress
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

메서드가 지정 된 디버그 주소에 대 한 정보를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetMethodFromAddress(  
   IDebugAddress* pAddress,  
   GUID*          pGuid,  
   DWORD*         pAppID,  
   _mdToken*      pTokenClass,  
   _mdToken*      pTokenMethod,  
   DWORD*         pdwOffset,  
   DWORD*         pdwVersion  
);  
```  
  
```c#  
int GetMethodFromAddress(  
   IDebugAddress pAddress,  
   out Guid      pGuid,  
   out uint      pAppID,  
   out uint      pTokenClass,  
   out uint      pTokenMethod,  
   out uint      pdwOffset,  
   out uint      pdwVersion  
);  
```  
  
#### 매개 변수  
 `pAddress`  
 \[in\] 디버그 표시 되며 주소는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.  
  
 `pGuid`  
 \[out\] 모듈의 고유 식별자입니다.  
  
 `pAppID`  
 \[out\] 응용 프로그램 도메인의 식별자입니다.  
  
 `pTokenClass`  
 \[out\] 토큰은 포함 하는 클래스를 나타냅니다.  
  
 `pTokenMethod`  
 \[out\] 토큰에 있는 모듈을 나타냅니다.  
  
 `pdwOffset`  
 \[out\] 시작 부분에서 바이트 오프셋에서 `pAddress` 매개 변수.  
  
 `pdwVersion`  
 \[out\] 버전 번호는 방법입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)