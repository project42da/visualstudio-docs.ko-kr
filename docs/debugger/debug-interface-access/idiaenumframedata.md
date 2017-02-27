---
title: "IDiaEnumFrameData | Microsoft Docs"
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
  - "IDiaEnumFrameData 인터페이스"
ms.assetid: 2ca7fd5a-b2fa-4b3a-9492-0263eafc435b
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# IDiaEnumFrameData
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

데이터 원본에 포함 된 다양 한 프레임 데이터 요소를 열거 합니다.  
  
## 구문  
  
```  
IDiaEnumFrameData : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDiaEnumFrameData`.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaEnumFrameData::get\_\_NewEnum](../../debugger/debug-interface-access/idiaenumframedata-get-newenum.md)|검색은 `IEnumVARIANT Interface` 이 열거자의 버전입니다.|  
|[IDiaEnumFrameData::get\_Count](../../debugger/debug-interface-access/idiaenumframedata-get-count.md)|프레임 데이터 요소 수를 검색합니다.|  
|[IDiaEnumFrameData::Item](../../debugger/debug-interface-access/idiaenumframedata-item.md)|프레임 데이터 요소는 인덱스를 사용 하 여 검색합니다.|  
|[IDiaEnumFrameData::Next](../../debugger/debug-interface-access/idiaenumframedata-next.md)|프레임 데이터 요소가 열거 시퀀스에서 지정 된 수를 검색합니다.|  
|[IDiaEnumFrameData::Skip](../../debugger/debug-interface-access/idiaenumframedata-skip.md)|프레임 데이터 요소가 열거 시퀀스에서 지정 된 수를 건너뜁니다.|  
|[IDiaEnumFrameData::Reset](../../debugger/debug-interface-access/idiaenumframedata-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[IDiaEnumFrameData::Clone](../../debugger/debug-interface-access/idiaenumframedata-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
|[IDiaEnumFrameData::frameByRVA](../../debugger/debug-interface-access/idiaenumframedata-framebyrva.md)|상대 가상 주소 \(RVA\)로 반환합니다.|  
|[IDiaEnumFrameData::frameByVA](../../debugger/debug-interface-access/idiaenumframedata-framebyva.md)|가상 주소 \(VA\)에서 프레임을 반환합니다.|  
  
## 설명  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스에서 구할에서 [IDiaSession::getEnumTables](../../debugger/debug-interface-access/idiasession-getenumtables.md) 메서드.  자세한 내용은 예제를 참조 하십시오.  
  
## 예제  
 가져오는 방법을 보여 주는이 예제 \(의 `GetEnumFrameData` 함수\) 사용 \(는 `ShowFrameData` 함수\)는 `IDiaEnumFrameData` 인터페이스입니다.  참조는 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) 인터페이스의 예는 `PrintFrameData` 함수입니다.  
  
```cpp#  
  
      IDiaEnumFrameData* GetEnumFrameData(IDiaSession *pSession)  
{  
    IDiaEnumFrameData* pUnknown    = NULL;  
    REFIID             iid         = __uuidof(IDiaEnumFrameData);  
    IDiaEnumTables*    pEnumTables = NULL;  
    IDiaTable*         pTable      = NULL;  
    ULONG              celt        = 0;  
  
    if (pSession->getEnumTables(&pEnumTables) != S_OK)  
    {  
        wprintf(L"ERROR - GetTable() getEnumTables\n");  
        return NULL;  
    }  
    while (pEnumTables->Next(1, &pTable, &celt) == S_OK && celt == 1)  
    {  
        // There is only one table that matches the given iid  
        HRESULT hr = pTable->QueryInterface(iid, (void**)&pUnknown);  
        pTable->Release();  
        if (hr == S_OK)  
        {  
            break;  
        }  
    }  
    pEnumTables->Release();  
    return pUnknown;  
}  
  
void ShowFrameData(IDiaSession *pSession)  
{  
    IDiaEnumFrameData* pEnumFrameData = GetEnumFrameData(pSession);;  
  
    if (pEnumFrameData != NULL)  
    {  
        IDiaFrameData* pFrameData;  
        ULONG celt = 0;  
  
        while(pEnumFrameData->Next(1, &pFrameData, &celt) == S_OK &&  
              celt == 1)  
        {  
            PrintFrameData(pFrameData);  
            pFrameData->Release();  
        }  
        pEnumFrameData->Release();   
    }  
}  
```  
  
## 요구 사항  
 **헤더:** Dia2.h  
  
 **라이브러리:** diaguids.lib  
  
 **DLL:** msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaSession::getEnumTables](../../debugger/debug-interface-access/idiasession-getenumtables.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)