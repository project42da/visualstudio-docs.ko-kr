---
title: "IDebugProperty3::GetStringChars | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProperty3::GetStringChars
helpviewer_keywords:
- IDebugProperty3::GetStringChars
ms.assetid: 832c37f3-85cb-4227-8ab2-f27a80eafe90
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: b743df25d0d17465de411211f5b0b6893bf67f9b
ms.openlocfilehash: a9433d9914f647c43d8190fb15fb35a99bf77a7b
ms.lasthandoff: 02/22/2017

---
# <a name="idebugproperty3getstringchars"></a>IDebugProperty3::GetStringChars
이 속성에 연결 된 문자열을 검색 하는 사용자가 제공한 버퍼에 저장 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetStringChars(  
   ULONG  buflen,  
   WCHAR* rgString,  
   ULONG* pceltFetched  
);  
```  
  
```c#  
int GetStringChars(  
   uint       buflen,   
   out string rgString,   
   out uint   pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `buflen`  
 [in] 최대 문자 수는 사용자가 제공한 버퍼를 보유할 수 있습니다.  
  
 `rgString`  
 [out] 문자열을 반환 합니다.  
  
 [C + +만], `rgString` 문자열의 유니코드 문자를 수신 하는 버퍼에 대 한 포인터입니다. 이 버퍼 이상 이어야 합니다 `buflen` 크기의 문자 (바이트 아님).  
  
 `pceltFetched`  
 [out] 여기서 실제 버퍼에 저장 하는 문자 수가 반환 됩니다. (수 `NULL` c + +에서.)  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>주의  
 C + +에서는 주의 해야 버퍼 이상 인지 시킬 수 있도록 `buflen` 자의 유니코드 문자입니다. 유니코드 문자가 2 바이트 길이의 않음을 유의 하십시오.  
  
> [!NOTE]
>  C + +에서 반환 된 문자열에는 null 종결 문자 포함 되지 않습니다. 주어진 경우 `pceltFetched` 문자열의 문자 수를 지정 합니다.  
  
## <a name="example"></a>예제  
 
```cpp  
CStringW RetrievePropertyString(IDebugProperty2 *pPropInfo)  
{  
    CStringW returnString = L"";  
    CComQIPtr<IDebugProperty3> pProp3 = pPropInfo->pProperty;  
    If (pProp3 != NULL) {  
        ULONG dwStrLen = 0;  
        HRESULT hr;  
        hr = pProp3->GetStringCharLength(&dwStrLen);  
        if (SUCCEEDED(hr) && dwStrLen > 0) {  
            ULONG dwRead;  
            CStrBufW buf(returnString,dwStrLen,CStrBuf::SET_LENGTH);  
            hr = pProp3->GetStringChars(dwStrLen,  
                                        reinterpret_cast<WCHAR*>(static_cast<CStringW::PXSTR>(buf)),  
                                        &dwRead);  
        }  
    }  
    return(returnString);
}
```    
  
## <a name="see-also"></a>참고 항목  
 [GetStringCharLength](../../../extensibility/debugger/reference/idebugproperty3-getstringcharlength.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
