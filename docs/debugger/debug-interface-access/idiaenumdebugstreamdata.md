---
title: "IDiaEnumDebugStreamData | Microsoft Docs"
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
  - "IDiaEnumDebugStreamData 인터페이스"
ms.assetid: e2023c32-4c05-4d0c-a0be-f016a230c788
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IDiaEnumDebugStreamData
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

레코드의 디버그 데이터 스트림 액세스를 제공합니다.  
  
## 구문  
  
```  
IDiaEnumDebugStreamData : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDiaEnumDebugStreamData`.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaEnumDebugStreamData::get\_\_NewEnum](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-newenum.md)|검색은 [IEnumVARIANT Interface](http://msdn.microsoft.com/ko-kr/139e3c93-faef-4003-9079-e0e94494db3e) 이 열거자의 버전입니다.|  
|[IDiaEnumDebugStreamData::get\_Count](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-count.md)|디버그 데이터 스트림 내의 레코드의 수를 검색합니다.|  
|[IDiaEnumDebugStreamData::get\_name](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-name.md)|디버그 데이터 스트림 이름을 검색합니다.|  
|[IDiaEnumDebugStreamData::Item](../../debugger/debug-interface-access/idiaenumdebugstreamdata-item.md)|지정된 된 레코드를 검색합니다.|  
|[IDiaEnumDebugStreamData::Next](../../debugger/debug-interface-access/idiaenumdebugstreamdata-next.md)|열거 시퀀스에서 지정 된 수의 레코드를 검색합니다.|  
|[IDiaEnumDebugStreamData::Skip](../../debugger/debug-interface-access/idiaenumdebugstreamdata-skip.md)|레코드는 열거 시퀀스에서 지정 된 수를 건너뜁니다.|  
|[IDiaEnumDebugStreamData::Reset](../../debugger/debug-interface-access/idiaenumdebugstreamdata-reset.md)|열거 시퀀스 시작 부분으로 다시 설정합니다.|  
|[IDiaEnumDebugStreamData::Clone](../../debugger/debug-interface-access/idiaenumdebugstreamdata-clone.md)|현재 열거자와 열거 된 시퀀스가 포함 하는 열거자를 만듭니다.|  
  
## 설명  
 이 인터페이스의 디버그 데이터 스트림 레코드 스트림을 나타냅니다.  크기 및 각 레코드의 해석 데이터 스트림을 가져온 레코드에 종속 됩니다.  이 인터페이스에 효과적으로 액세스 기호 파일에 원시 데이터 바이트 수를 제공합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 하는 [IDiaEnumDebugStreams::Item](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md) 또는 [IDiaEnumDebugStreams::Next](../../debugger/debug-interface-access/idiaenumdebugstreams-next.md) 방법으로 확인할 수는 `IDiaEnumDebugStreamData` 개체입니다.  
  
## 예제  
 단일 데이터 스트림과 해당 레코드에 액세스 하는 방법을 보여 주는이 예제입니다.  
  
```cpp#  
void PrintStreamData(IDiaEnumDebugStreamData* pStream)  
{  
    BSTR  wszName;  
    LONG  dwElem;  
    ULONG celt    = 0;  
    DWORD cbData;  
    DWORD cbTotal = 0;  
    BYTE  data[1024];  
  
    if(pStream->get_name(&wszName) != S_OK)  
    {  
        wprintf_s(L"ERROR - PrintStreamData() get_name\n");  
    }  
    else  
    {  
        wprintf_s(L"Stream: %s", wszName);  
        SysFreeString(wszName);  
    }  
    if(pStream->get_Count(&dwElem) != S_OK)  
    {  
        wprintf(L"ERROR - PrintStreamData() get_Count\n");  
    }  
    else  
    {  
        wprintf(L"(%d)\n", dwElem);  
    }  
    while(pStream->Next(1, sizeof(data), &cbData, (BYTE *)&data, &celt) == S_OK)  
    {  
        DWORD i;  
        for (i = 0; i < cbData; i++)  
        {  
            wprintf(L"%02X ", data[i]);  
            if(i && i % 8 == 7 && i+1 < cbData)  
            {  
                wprintf(L"- ");  
            }  
        }  
        wprintf(L"| ");  
        for(i = 0; i < cbData; i++)  
        {  
            wprintf(L"%c", iswprint(data[i]) ? data[i] : '.');  
        }  
        wprintf(L"\n");  
        cbTotal += cbData;  
    }  
    wprintf(L"Summary :\n\tSizeof(Elem) = %d\n\tNo of Elems = %d\n\n",  
            cbTotal/dwElem, dwElem);  
}  
```  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaEnumDebugStreams::Item](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md)   
 [IDiaEnumDebugStreams::Next](../../debugger/debug-interface-access/idiaenumdebugstreams-next.md)