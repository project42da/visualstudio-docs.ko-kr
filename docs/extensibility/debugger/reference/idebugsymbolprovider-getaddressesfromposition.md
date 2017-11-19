---
title: IDebugSymbolProvider::GetAddressesFromPosition | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugSymbolProvider::GetAddressesFromPosition
helpviewer_keywords: IDebugSymbolProvider::GetAddressesFromPosition method
ms.assetid: 1b0f02cb-8ace-4614-88f3-0e10239012b3
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a4d5c4b59b8e56faf5177256b32cca191ba5031d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugsymbolprovidergetaddressesfromposition"></a>IDebugSymbolProvider::GetAddressesFromPosition
이 메서드는 디버그 주소 배열로 문서 위치를 매핑합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetAddressesFromPosition(   
   IDebugDocumentPosition2* pDocPos,  
   BOOL                     fStatmentOnly,  
   IEnumDebugAddresses**    ppEnumBegAddresses,  
   IEnumDebugAddresses**    ppEnumEndAddresses  
);  
```  
  
```csharp  
int GetAddressesFromPosition(   
   IDebugDocumentPosition2  pDocPos,  
   bool                     fStatmentOnly,  
   out IEnumDebugAddresses  ppEnumBegAddresses,  
   out IEnumDebugAddresses  ppEnumEndAddresses  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pDocPos`  
 [in] 문서 위치입니다.  
  
 `fStatmentOnly`  
 [in] True 인 경우, 단일 문으로 디버그 주소를 제한 합니다.  
  
 `ppEnumBegAddresses`  
 [out] 이 문 또는 줄와 관련 된 디버그 시작 주소에 대 한 열거자를 반환 합니다.  
  
 `ppEnumEndAddresses`  
 [out] 반환 된 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) 관련 된이 문 또는 줄 끝 디버그 주소에 대 한 열거자입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 문서 위치는 일반적으로 다양 한 소스 줄을 나타냅니다. 이 방법은 제공 시작 및 끝 주소 디버그가이 줄 합니다. 일부 언어에는 여러 줄 또는 둘 이상의 문을 포함 하는 줄에 걸쳐 있는 문을 허용 합니다. 이 메서드는 단일 문으로 디버그 주소를 제한 하는 플래그를 제공 합니다.  
  
 서식 파일의 경우 처럼 여러 디버그 주소 단일 문에 대 한 것 같습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md)   
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)