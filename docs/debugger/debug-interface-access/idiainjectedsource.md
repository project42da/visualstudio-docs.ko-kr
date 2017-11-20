---
title: IDiaInjectedSource | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaInjectedSource interface
ms.assetid: 75192c5c-812d-4675-9dc5-4c2cff3ba503
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7beda305bbe0673b6e1b47f0e11eb641ab8aa0d5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiainjectedsource"></a>IDiaInjectedSource
액세스는 DIA 데이터 원본에 저장 하는 소스 코드를 삽입 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDiaInjectedSource : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDiaInjectedSource`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDiaInjectedSource::get_crc](../../debugger/debug-interface-access/idiainjectedsource-get-crc.md)|소스 코드의 바이트에서 계산 된 순환 중복 검사 (CRC)를 검색 합니다.|  
|[IDiaInjectedSource::get_length](../../debugger/debug-interface-access/idiainjectedsource-get-length.md)|코드의 바이트 수를 검색 합니다.|  
|[IDiaInjectedSource::get_filename](../../debugger/debug-interface-access/idiainjectedsource-get-filename.md)|원본에 대 한 파일 이름을 검색합니다.|  
|[IDiaInjectedSource::get_objectFilename](../../debugger/debug-interface-access/idiainjectedsource-get-objectfilename.md)|소스 컴파일한 개체 파일 이름을 검색 합니다.|  
|[IDiaInjectedSource::get_virtualFilename](../../debugger/debug-interface-access/idiainjectedsource-get-virtualfilename.md)|파일이 아닌 소스 코드;에 지정 된 이름 검색 즉, 삽입 된 코드는 합니다.|  
|[IDiaInjectedSource::get_sourceCompression](../../debugger/debug-interface-access/idiainjectedsource-get-sourcecompression.md)|소스 압축 사용 표시기를 검색 합니다.|  
|[IDiaInjectedSource::get_source](../../debugger/debug-interface-access/idiainjectedsource-get-source.md)|소스 코드 바이트를 검색합니다.|  
  
## <a name="remarks"></a>설명  
 삽입 된 원본은 컴파일하는 동안 삽입 된 텍스트입니다. 이 전처리기를 의미 하지 `#include` c + +에서 사용 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 가져올는 [idiaenuminjectedsources:: Item](../../debugger/debug-interface-access/idiaenuminjectedsources-item.md) 또는 [idiaenuminjectedsources:: Next](../../debugger/debug-interface-access/idiaenuminjectedsources-next.md) 메서드. 참조는 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md) 인터페이스 가져오기에 대 한 예제는 `IDiaInjectedSource` 인터페이스입니다.  
  
## <a name="example"></a>예제  
 사용할 수 있는 데이터를 표시 하는이 예제는 `IDiaInjectedSource` 인터페이스입니다. 사용 하 여 다른 방법에 대 한는 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md) 인터페이스에서 예제를 참조 하십시오.는 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md) 인터페이스입니다.  
  
```C++  
void PrintInjectedSource(IDiaInjectedSource* pSource)  
{  
    ULONGLONG codeLength      = 0;  
    DWORD     crc             = 0;  
    DWORD     compressionType = 0;  
    BSTR      sourceFilename  = NULL;  
    BSTR      objectFilename  = NULL;  
    BSTR      virtualFilename = NULL;  
  
    std::cout << "Injected Source:" << std::endl;  
    if (pSource != NULL)  
    {  
        if (pSource->get_crc(&crc) == S_OK &&  
            pSource->get_sourceCompression(&compressionType) == S_OK &&  
            pSource->get_length(&codeLength) == S_OK)  
        {  
            wprintf(L"  crc = %lu\n", crc);  
            wprintf(L"  code length = %I64u\n",codeLength);  
            wprintf(L"  compression type code = %lu\n", compressionType);  
        }  
  
        wprintf(L"  source filename: ");  
        if (pSource->get_filename(&sourceFilename) == S_OK)  
        {  
            wprintf(L"%s", sourceFilename);  
        }  
        else  
        {  
            wprintf(L"<none>");  
        }  
        wprintf(L"\n");  
  
        wprintf(L"  object filename: ");  
        if (pSource->get_filename(&objectFilename) == S_OK)  
        {  
            wprintf(L"%s", objectFilename);  
        }  
        else  
        {  
            wprintf(L"<none>");  
        }  
        wprintf(L"\n");  
  
        wprintf(L"  virtual filename: ");  
        if (pSource->get_filename(&virtualFilename) == S_OK)  
        {  
            wprintf(L"%s", virtualFilename);  
        }  
        else  
        {  
            wprintf(L"<none>");  
        }  
        wprintf(L"\n");  
  
        SysFreeString(sourceFilename);  
        SysFreeString(objectFilename);  
        SysFreeString(virtualFilename);  
    }  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenuminjectedsources:: Item](../../debugger/debug-interface-access/idiaenuminjectedsources-item.md)   
 [Idiaenuminjectedsources:: Next](../../debugger/debug-interface-access/idiaenuminjectedsources-next.md)   
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)