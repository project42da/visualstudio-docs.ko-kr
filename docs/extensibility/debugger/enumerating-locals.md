---
title: "지역 변수를 열거합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK], 지역 변수를 열거 합니다."
  - "식 계산, 지역 변수를 열거 합니다."
ms.assetid: 254a88e7-d3a7-447a-bd0c-8985e73d85cf
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# 지역 변수를 열거합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 Visual Studio을 채울 경우는 **지역** 호출 창 [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) 에 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 개체에서 반환 된 [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) \(참조 [GetMethodProperty 구현](../../extensibility/debugger/implementing-getmethodproperty.md)\).`IDebugProperty2::EnumChildren` 반환 된 [IEnumDebugPropertyInfo2](../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) 개체입니다.  
  
 이 구현 `IDebugProperty2::EnumChildren` 다음 작업을 수행 합니다.  
  
1.  메서드를 나타내는이 확인 합니다.  
  
2.  사용 하는 `guidFilter` 에 대해 호출할 메서드를 결정 하는 인수는 [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) 개체입니다. 경우 `guidFilter` 같음:  
  
    1.  `guidFilterLocals`, 를 호출 [EnumLocals](../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) 얻을 수는 [IEnumDebugFields](../../extensibility/debugger/reference/ienumdebugfields.md) 개체입니다.  
  
    2.  `guidFilterArgs`, 를 호출 [EnumArguments](../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) 얻을 수는 `IEnumDebugFields` 개체입니다.  
  
    3.  `guidFilterLocalsPlusArgs`, 결과를 결합 하는 열거형을 합성 `IDebugMethodField::EnumLocals` 및 `IDebugMethodField::EnumArguments`합니다. 클래스로 표현 되는이 합성 `CEnumMethodField`합니다.  
  
3.  클래스를 인스턴스화합니다 \(라는 `CEnumPropertyInfo` 이 예에서\)를 구현 하는 `IEnumDebugPropertyInfo2` 인터페이스를 포함는 `IEnumDebugFields` 개체입니다.  
  
4.  반환 된 `IEnumDebugProperty2Info2` 에서 인터페이스는 `CEnumPropertyInfo` 개체입니다.  
  
## 관리 코드  
 이 예의 구현을 보여 줍니다. `IDebugProperty2::EnumChildren` 관리 코드에서.  
  
```c#  
namespace EEMC  
{  
    public class CFieldProperty : IDebugProperty2  
    {  
        public HRESULT EnumChildren (  
                uint                    dwFields,  
                uint                    radix,  
            ref Guid                    guidFilter,   
                ulong                   attribFilter,   
                string                  nameFilter,   
                uint                    timeout,  
            out IEnumDebugPropertyInfo2 properties)   
        {  
            properties = null;  
            IEnumDebugFields fields = null;  
  
            // If this field is a method...  
            if (0 != ((uint) fieldKind & (uint) FIELD_KIND.FIELD_TYPE_METHOD))  
            {  
                IDebugMethodField methodField = (IDebugMethodField) field;  
  
                // Enumerate parameters.  
                if (guidFilter == FilterGuids.guidFilterArgs)  
                {  
                    methodField.EnumParameters(out fields);    
                }  
                // Enumerate local variables.  
                else if (guidFilter == FilterGuids.guidFilterLocals)  
                {  
                    methodField.EnumLocals(address, out fields);    
                }  
                // Enumerate all local variables, including invisible compiler temps.  
                else if (guidFilter == FilterGuids.guidFilterAllLocals)  
                {  
                    methodField.EnumAllLocals(address, out fields);    
                }  
                // Enumerate "this", if any, and all parameters and local variables.  
                else if (guidFilter == FilterGuids.guidFilterLocalsPlusArgs)  
                {  
                    IDebugClassField fieldThis   = null;  
                    IEnumDebugFields parameters = null;  
                    IEnumDebugFields locals     = null;  
  
                    methodField.GetThis(out fieldThis);  
                    methodField.EnumParameters(out parameters);  
                    methodField.EnumLocals(address, out locals);  
  
                    CEnumMethodField enumMethodField =   
                        new CEnumMethodField(fieldThis, parameters, locals);  
                    fields = (IEnumDebugFields) enumMethodField;  
                }  
                // Enumerate only "this".  
                else if (guidFilter == FilterGuids.guidFilterThis)  
                {  
                    IDebugClassField fieldThis   = null;  
                    methodField.GetThis(out fieldThis);  
  
                    CEnumMethodField enumMethodField =   
                        new CEnumMethodField(fieldThis, null, null);  
                    fields = (IEnumDebugFields) enumMethodField;  
                }  
                else throw new COMException();// E_FAIL  
            }  
            // Wrap a property enumerator around the field enumerator.  
            CEnumPropertyInfo propertiesInfo =   
                new CEnumPropertyInfo(provider, address, binder, radix, fields,   
                 (DEBUGPROP_INFO_FLAGS) dwFields);  
  
            properties = (IEnumDebugPropertyInfo2) propertiesInfo;  
            return COM.S_OK;  
        }  
    }  
}  
```  
  
## 관리 되지 않는 코드  
 이 예의 구현을 보여 줍니다. `IDebugProperty2::EnumChildren` 비관리 코드에서.  
  
```cpp#  
STDMETHODIMP CFieldProperty::EnumChildren(   
        in DEBUGPROP_INFO_FLAGS        infoFlags,  
        in DWORD                       radix,  
        in REFGUID                     guidFilter,  
        in DBG_ATTRIB_FLAGS            attribFilter,  
        in LPCOLESTR                   pszNameFilter,  
        in DWORD                       timeout,  
        out IEnumDebugPropertyInfo2 ** ppchildren )  
{  
    if (ppchildren == NULL)  
        return E_INVALIDARG;  
    else  
        *ppchildren = 0;  
  
    //get enumeration  
    HRESULT hr;  
    IEnumDebugFields*     pfields    = NULL;  
  
    if (m_fieldKind & FIELD_TYPE_METHOD)  
    {  
        //-----------------------------------------------------  
        // A Method  
  
        IDebugMethodField*  pmethod    = NULL;  
  
        //enumerate the requested properties  
        hr = m_field->QueryInterface( IID_IDebugMethodField,  
            reinterpret_cast<void**>(&pmethod) );  
        if (FAILED(hr))  
            return hr;  
  
        if (guidFilter == guidFilterArgs)  
        {  
            hr = pmethod->EnumParameters( &pfields );    
        }  
        else if (guidFilter == guidFilterLocals)  
        {  
            hr = pmethod->EnumLocals( m_address, &pfields );  
        }  
        else if (guidFilter == guidFilterAllLocals)  
        {  
            hr = pmethod->EnumAllLocals( m_address, &pfields );  
        }  
        else if (guidFilter == guidFilterLocalsPlusArgs)  
        {  
            //we create a special enumerator for this  
            IDebugClassField* pfieldThis  = NULL;  
            IEnumDebugFields* pparameters = NULL;  
            IEnumDebugFields* plocals     = NULL;  
  
            pmethod->GetThis( &pfieldThis );  
            pmethod->EnumParameters( &pparameters );  
            pmethod->EnumLocals( m_address, &plocals );  
  
            CEnumMethodField* penumMethodField =  
                new CEnumMethodField( pfieldThis, pparameters, plocals );  
            if (pfieldThis != NULL)  
                pfieldThis->Release();  
            if (pparameters != NULL)  
                pparameters->Release();  
            if (plocals != NULL)  
                plocals->Release();  
            if (!penumMethodField)   
            {   
                hr = E_OUTOFMEMORY;  
            }  
            else  
            {  
                hr = penumMethodField->QueryInterface( IID_IEnumDebugFields,  
                        reinterpret_cast<void**>(&pfields) );  
                penumMethodField->Release();  
            }  
        }  
        else if (guidFilter == guidFilterThis )  
        {  
            IDebugClassField* pfieldThis  = NULL;  
  
            hr = pmethod->GetThis( &pfieldThis );  
            if (SUCCEEDED(hr))  
            {  
                CEnumMethodField* penumMethodField =  
                    new CEnumMethodField( pfieldThis, NULL, NULL );  
                pfieldThis->Release();  
                if (!penumMethodField)   
                {  
                    hr = E_OUTOFMEMORY;  
                }  
                else  
                {  
                    hr = penumMethodField->QueryInterface( IID_IEnumDebugFields,  
                        reinterpret_cast<void**>(&pfields) );  
                    penumMethodField->Release();  
                }  
            }  
        }  
        else  
        {  
            hr = E_FAIL;  
        }  
  
        pmethod->Release();  
        if (hr != S_OK)  
            return hr;  
    }  
  
    //create a property info enumeration around the field enumerator  
    CEnumPropertyInfo* pproperties =  
        new CEnumPropertyInfo( m_provider, m_address, m_binder,   
                               radix, pfields, infoFlags );  
    if (pfields != NULL)  
        pfields->Release();  
    if (pproperties == NULL)  
        return E_OUTOFMEMORY;  
  
    hr = pproperties->QueryInterface( IID_IEnumDebugPropertyInfo2,  
        reinterpret_cast<void**>(ppchildren) );  
    pproperties->Release();  
  
    return hr;  
}  
```  
  
## 참고 항목  
 [지역 변수의 샘플 구현](../../extensibility/debugger/sample-implementation-of-locals.md)   
 [GetMethodProperty 구현](../../extensibility/debugger/implementing-getmethodproperty.md)   
 [평가 컨텍스트](../../extensibility/debugger/evaluation-context.md)