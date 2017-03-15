---
title: "IDiaEnumDebugStreamData::Next | Microsoft Docs"
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
  - "IDiaEnumDebugStreamData::Next 메서드"
ms.assetid: 114171dd-38fd-4bd7-a702-8ff887ffc99b
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumDebugStreamData::Next
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

레코드 열거 시퀀스에서 지정 된 수를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT Next (   
   ULONG  celt,  
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[],  
   ULONG* pceltFetched  
);  
```  
  
#### 매개 변수  
 celt  
 \[in\] 검색할 레코드의 수입니다.  
  
 사용  
 \[in\] 데이터 버퍼에서 바이트 단위의 크기입니다.  
  
 pcbData  
 \[out\] 반환 된 바이트 수를 반환 합니다.  경우 `data` NULL, 다음이 `pcbData` 요청한 모든 레코드에 대 한 총 사용 가능한 데이터의 바이트 수를 포함 합니다.  
  
 데이터\]  
 \[out\] 디버그 스트림을 레코드 데이터로 채울 버퍼입니다.  
  
 pceltFetched  
 \[in, out\] 레코드 수를 반환 합니다. `data`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 레코드가 더 이상 없으면.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)   
 [IDiaEnumDebugStreams::Next](../../debugger/debug-interface-access/idiaenumdebugstreams-next.md)