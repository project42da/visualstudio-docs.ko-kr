---
title: "IDiaStackWalkHelper::pdataForVA | Microsoft Docs"
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
  - "IDiaStackWalkHelper2::pdataByVA 메서드"
ms.assetid: fafc38fe-74dc-4726-9a51-eebf3a673d7f
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# IDiaStackWalkHelper::pdataForVA
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

가상 주소와 관련 된 PDATA 데이터 블록을 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT pdataForVA(   
   ULONGLONG  va,  
   DWORD      cbData,  
   DWORD*     pcbData,  
   BYTE*      pbData  
);  
```  
  
#### 매개 변수  
 `va`  
 \[in\] 가상 주소를 얻을 수 있는 데이터를 지정 합니다.  
  
 `cbData`  
 \[in\] 데이터의 바이트 수를 구하려면 크기입니다.  
  
 `pcbData`  
 \[out\] 데이터의 실제 크기에서 가져온 바이트를 반환 합니다.  
  
 `pbData`  
 \[in, out\] 요청 된 데이터를 사용 하 여 채워진 버퍼입니다.  `NULL`일 수 없습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 없음 PDATA 지정 된 주소에 대 한 경우입니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 PDATA \(구역 "으로 구성 된.pdata" 라는\) 예외 처리에 대 한 함수에 대 한 정보는 컴파일 대상에 포함 되어 있습니다.  
  
 호출자가 얼마나 많은 데이터를 사용할 수 있습니다에 게 요청 하지 않아도 되므로 반환 될 데이터의 양을 호출자에 게 알 수 있습니다.  따라서 가능한 경우 오류를 반환 합니다.이 메서드의 구현에 대 한 것은 `pbData` 매개 변수가 `NULL`.  
  
## 참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)