---
title: "IDiaPropertyStorage | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaPropertyStorage 인터페이스"
ms.assetid: d3197a38-5973-4e56-873e-4f1b84c3f674
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IDiaPropertyStorage
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

영구 DIA 속성 집합의 속성을 읽을 수 있습니다.  
  
## 구문  
  
```  
IDiaPropertyStorage : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDiaPropertyStorage`.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaPropertyStorage::Enum](../../debugger/debug-interface-access/idiapropertystorage-enum.md)|이 집합 내에서 속성에 대 한 열거자를에 대 한 포인터를 가져옵니다.|  
|[IDiaPropertyStorage::ReadBOOL](../../debugger/debug-interface-access/idiapropertystorage-readbool.md)|읽고 `BOOL` 속성 집합 값입니다.|  
|[IDiaPropertyStorage::ReadBSTR](../../debugger/debug-interface-access/idiapropertystorage-readbstr.md)|읽고 `BSTR` 속성 집합 값입니다.|  
|[IDiaPropertyStorage::ReadDWORD](../../debugger/debug-interface-access/idiapropertystorage-readdword.md)|읽고 `DWORD` 속성 집합 값입니다.|  
|[IDiaPropertyStorage::ReadLONG](../../debugger/debug-interface-access/idiapropertystorage-readlong.md)|읽고 `LONG` 속성 집합 값입니다.|  
|[IDiaPropertyStorage::ReadMultiple](../../debugger/debug-interface-access/idiapropertystorage-readmultiple.md)|속성 집합에 속성 값을 읽습니다.|  
|[IDiaPropertyStorage::ReadPropertyNames](../../debugger/debug-interface-access/idiapropertystorage-readpropertynames.md)|가져옵니다 해당 문자열 이름에 대 한 속성 식별자를 지정 합니다.|  
|[IDiaPropertyStorage::ReadULONGLONG](../../debugger/debug-interface-access/idiapropertystorage-readulonglong.md)|읽고 `ULONGLONG` 속성 집합 값입니다.|  
  
## 설명  
 속성 집합 내의 각 속성에는 속성 식별자 \(ID\), 4 바이트 식별 됩니다 `ULONG` 해당 집합에는 고유 값입니다.  속성을 통해 노출 되는 `IDiaPropertyStorage` 인터페이스에 부모 인터페이스에서 사용할 수 있는 속성에 해당 합니다.  그러나 예를 들어, 속성을의 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 인터페이스를 통해 이름으로 액세스할 수는 `IDiaPropertyStorage` 인터페이스 \(속성에 액세스할 수 있지만에 대 한 특정 속성이 유효 않는다는 것 있습니다 `IDiaSymbol` 개체\).  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 얻을 `QueryInterface` 다른 인터페이스에서 메서드.  다음 인터페이스를 쿼리할 수 있는 `IDiaPropertyStorage` 인터페이스:  
  
-   [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)  
  
-   [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)  
  
-   [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)  
  
-   [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)  
  
-   [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)  
  
-   [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)  
  
-   [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)  
  
## 예제  
 노출 된 모든 속성을 표시 하는 함수를 보여 주는이 예제는 `IDiaPropertyStorage` 개체입니다.  참조는 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md) 인터페이스를 하는 방법의 예를 `IDiaPropertyStorage` 인터페이스에서 얻은 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md) 인터페이스.  
  
```cpp#  
void PrintPropertyStorage(IDiaPropertyStorage* pPropertyStorage)  
{  
    IEnumSTATPROPSTG* pEnumProps;  
    STATPROPSTG       prop;  
    DWORD             celt = 1;  
  
    if (pPropertyStorage->Enum(&pEnumProps) == S_OK)  
    {  
        while (pEnumProps->Next(celt, &prop, &celt) == S_OK)  
        {  
            PROPSPEC pspec = { PRSPEC_PROPID, prop.propid };  
            PROPVARIANT vt = { VT_EMPTY };  
  
            if (pPropertyStorage->ReadMultiple( 1, &pspec, &vt) == S_OK)  
            {  
                switch( vt.vt ){  
                    case VT_BOOL:  
                        wprintf( L"%32s:\t %s\n", prop.lpwstrName, vt.bVal ? L"true" : L"false" );  
                        break;  
                    case VT_I2:  
                        wprintf( L"%32s:\t %d\n", prop.lpwstrName, vt.iVal );  
                        break;  
                    case VT_UI2:  
                        wprintf( L"%32s:\t %d\n", prop.lpwstrName, vt.uiVal );  
                        break;  
                    case VT_I4:  
                        wprintf( L"%32s:\t %d\n", prop.lpwstrName, vt.intVal );  
                        break;  
                    case VT_UI4:  
                        wprintf( L"%32s:\t 0x%0x\n", prop.lpwstrName, vt.uintVal );  
                        break;  
                    case VT_UI8:  
                        wprintf( L"%32s:\t 0x%x\n", prop.lpwstrName, vt.uhVal.QuadPart );  
                        break;  
                    case VT_BSTR:  
                        wprintf( L"%32s:\t %s\n", prop.lpwstrName, vt.bstrVal );  
                        break;  
                    case VT_UNKNOWN:  
                        wprintf( L"%32s:\t %p\n", prop.lpwstrName, vt.punkVal );  
                        break;  
                    case VT_SAFEARRAY:  
                        break;  
                    default:  
                       break;  
                }  
                VariantClear((VARIANTARG*) &vt);  
            }  
        }  
        pEnumProps->Release();  
    }  
}  
```  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaSession::getEnumTables](../../debugger/debug-interface-access/idiasession-getenumtables.md)   
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)   
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)   
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)