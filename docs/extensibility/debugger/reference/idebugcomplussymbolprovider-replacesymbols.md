---
title: IDebugComPlusSymbolProvider::ReplaceSymbols | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ReplaceSymbols
- IDebugComPlusSymbolProvider::ReplaceSymbols
ms.assetid: 82fbc8db-c4b1-432f-bec9-1a9dc09570be
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f4afd217521e19468db984d085fc55b568e891ce
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugcomplussymbolproviderreplacesymbols"></a>IDebugComPlusSymbolProvider::ReplaceSymbols
지정된 된 데이터 스트림에 설정과 현재 디버그 기호를 바꿉니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ReplaceSymbols(  
   ULONG32  ulAppDomainID,  
   GUID     guidModule,  
   IStream* pStream  
);  
```  
  
```csharp  
int ReplaceSymbols(  
   uint    ulAppDomainID,  
   Guid    guidModule,  
   IStream pStream  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ulAppDomainID`  
 [in] 응용 프로그램 도메인의 식별자입니다.  
  
 `guidModule`  
 [in] 모듈의 고유 식별자입니다.  
  
 `pStream`  
 [in] 새 기호를 포함 하는 데이터 스트림.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에 대 한이 메서드를 구현 하는 방법을 보여 줍니다는 **CDebugSymbolProvider** 공개 하는 개체는 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) 인터페이스입니다.  
  
```cpp  
HRESULT CDebugSymbolProvider::ReplaceSymbols(  
    ULONG32 ulAppDomainID,  
    GUID guidModule,  
    IStream* pStream  
)  
{  
    HRESULT hr = S_OK;  
    CComPtr<CModule> pModule;  
    Module_ID idModule(ulAppDomainID, guidModule);  
  
    METHOD_ENTRY( CDebugSymbolProvider::ReplaceSymbols );  
  
    IfFailGo( GetModule( idModule, &pModule ) );  
    IfFailGo( pModule->ReplaceSymbols( pStream ) );  
  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::ReplaceSymbols, hr );  
    return hr;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)