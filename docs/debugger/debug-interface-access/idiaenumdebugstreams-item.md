---
title: "IDiaEnumDebugStreams::Item | Microsoft Docs"
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
  - "IDiaEnumDebugStreams::Item 메서드"
ms.assetid: 6b388fe1-eabc-4720-9d59-dc09b0ceaeac
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaEnumDebugStreams::Item
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

으로 인덱스 또는 이름을 디버그 스트림을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT Item (   
   VARIANT                   index,  
   IDiaEnumDebugStreamData** stream  
);  
```  
  
#### 매개 변수  
 인덱스\(index\)  
 \[in\] 인덱스 또는 이름을 디버그 스트림을 검색 합니다.  정수 변수를 사용 하는 경우 범위가 0 이어야 합니다 `count`\-1, 어디 `count` 에서 반환 하는 것의 [IDiaEnumDebugStreams::get\_Count](../../debugger/debug-interface-access/idiaenumdebugstreams-get-count.md) 메서드.  
  
 스트림\(stream\)  
 \[out\] 반환 된 [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md) 지정 된 디버그 스트림을 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 예제  
  
```cpp#  
IDiaEnumDebugStreamData *GetStreamData(IDiaEnumDebugStreams *pStreamList,  
                                       LONG whichStream)  
{  
    IDiaEnumDebugStreamData *pStreamData = NULL;  
    if (pStreamList != NULL)  
    {  
        LONG numStreams = 0;  
        if (pStreamList->get_count(&numStreams) == S_OK &&  
            whichStream >= 0 && whichStream < numStreams)  
        {  
            VARIANT vIndex;  
            vIndex.vt   = VT_I4;  
            vIndex.lVal = whichStream;  
            if (pStreamList->Item(vIndex,&pStreamData) != S_OK)  
            {  
                 std::cerr << "Error retrieving stream " << whichStream << std::endl;  
            }  
        }  
    }  
    return(pStreamData);  
}  
```  
  
## 참고 항목  
 [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)   
 [IDiaEnumDebugStreams](../../debugger/debug-interface-access/idiaenumdebugstreams.md)