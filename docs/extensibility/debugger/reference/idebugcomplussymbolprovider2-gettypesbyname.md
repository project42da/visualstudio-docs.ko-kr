---
title: "IDebugComPlusSymbolProvider2::GetTypesByName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GetTypesByName"
  - "IDebugComPlusSymbolProvider2::GetTypesByName"
ms.assetid: ef76b1a8-6910-48fe-b4af-d9045eefd23f
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugComPlusSymbolProvider2::GetTypesByName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이름이 지정 된 형식을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetTypesByName(  
   LPCOLESTR          pszClassName,  
   NAME_MATCH         nameMatch,  
   IEnumDebugFields** ppEnum  
);  
```  
  
```c#  
int GetTypesByName(  
   string               pszClassName,  
   enum_ NAME_MATCH     nameMatch,  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszClassName`  
 [in] 형식의 이름입니다.  
  
 `nameMatch`  
 [in] 유형과 일치 하는 예를 들어 대/소문자 구분을 선택합니다. 값은 [NAME_MATCH](../../../extensibility/debugger/reference/name-match.md) 열거형입니다.  
  
 `ppEnum`  
 [out] 지정 된 이름의 형식을 포함 하는 열거자입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>주의  
 제네릭 형식에 대해 검색할 이름이 ' 목록 \< int>' 또는 '목록 \< int, int >'는 '목록' 것입니다. 이름이 같은 유형의 여러 모듈에서 표시 하는 경우는 `ppEnum` 매개 변수 복사본을 모두 포함 됩니다. 사용 해야 [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md) 에 따라 구분 하 고는 `guidModule` 매개 변수입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서이 메서드를 구현 하는 방법을 한 **CDebugSymbolProvider** 개체를 노출 하는 [IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md) 인터페이스입니다.  
  
```cpp#  
HRESULT CDebugSymbolProvider::GetTypesByName(  
    LPCOLESTR pszClassName,  
    NAME_MATCH nameMatch,  
    IEnumDebugFields** ppEnum  
)  
{  
    HRESULT hr = S_OK;  
    CModIter ModIter;  
    CModule* pmodule; // the iterator owns the reference  
    CFieldList listField;  
  
    ASSERT(IsValidWideStringPtr(pszClassName));  
    ASSERT(IsValidWritePtr(ppEnum, IEnumDebugFields*));  
  
    METHOD_ENTRY( CDebugSymbolProvider::GetTypesByName );  
  
    IfFalseGo( pszClassName && ppEnum, E_INVALIDARG );  
    *ppEnum = NULL;  
  
    IfFailGo( GetModuleIter(&ModIter) );  
  
    hr = S_FALSE;  
  
    if ( nameMatch == nmCaseInsensitive)  
    {  
        while (ModIter.GetNext(&pmodule))  
        {  
            if (pmodule->FindTypesByNameCaseInsensitive( pszClassName,  
                    &listField,  
                    this ) )  
            {  
                hr = S_OK;  
            }  
        }  
    }  
    else  
    {  
        while (ModIter.GetNext(&pmodule))  
        {  
            if (pmodule->FindTypesByName( pszClassName,  
                                          &listField,  
                                          this) )  
            {  
                hr = S_OK;  
            }  
        }  
    }  
  
    // If the list is empty then no type  
    IfFalseGo( listField.GetCount(), E_FAIL );  
  
    // Create enumerator  
    IfFailGo( CreateEnumerator( ppEnum, &listField ) );  
  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::GetTypesByName, hr );  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md)