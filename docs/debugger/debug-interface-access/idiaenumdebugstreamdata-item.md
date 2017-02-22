---
title: "IDiaEnumDebugStreamData::Item | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaEnumDebugStreamData::Item 메서드"
ms.assetid: 761e61a5-44a6-4d5d-a98e-c2e9b89d2343
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaEnumDebugStreamData::Item
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정된 된 레코드를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT Item (   
   DWORD  index,  
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### 매개 변수  
 인덱스\(index\)  
 \[in\] 검색할 수 있는 레코드의 인덱스입니다.  인덱스는 범위가 0입니다 `count`\-1, 어디 `count` 반환 하는 [IDiaEnumDebugStreamData::get\_Count](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-count.md).  
  
 사용  
 \[in\] 데이터 버퍼에서 바이트 단위의 크기입니다.  
  
 pcbData  
 \[out\] 반환 된 바이트 수를 반환 합니다.  경우 `data` 입니다 `NULL`, 다음 `pcbData` 총 지정 된 레코드에 사용할 수 있는 데이터의 바이트 수를 포함 합니다.  
  
 데이터\]  
 \[out\] 디버그 스트림을 레코드 데이터를 사용 하 여 채워진 버퍼입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 `E_INVALIDARG` 에 대해 잘못 된 매개 변수가 경우는 `index` 매개 변수 범위 밖입니다.  
  
## 참고 항목  
 [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)   
 [IDiaEnumDebugStreamData::Next](../../debugger/debug-interface-access/idiaenumdebugstreamdata-next.md)   
 [IDiaEnumDebugStreams::Item](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md)   
 [IDiaEnumDebugStreamData::get\_Count](../../debugger/debug-interface-access/idiaenumdebugstreamdata-get-count.md)   
 [IDiaEnumDebugStreamData::Skip](../../debugger/debug-interface-access/idiaenumdebugstreamdata-skip.md)