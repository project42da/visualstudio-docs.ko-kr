---
title: "IDiaFrameData::get_allocatesBasePointer | Microsoft Docs"
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
  - "IDiaFrameData::get_allocatesBasePointer 메서드"
ms.assetid: 8a33db5d-008c-4fe5-b64f-210c9b77f686
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaFrameData::get_allocatesBasePointer
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

코드에서이 주소 범위에 대 한 기본 포인터 할당 되었는지 여부를 나타내는 플래그를 검색 합니다.  이 메서드는 사용되지 않습니다.  
  
## 구문  
  
```cpp#  
HRESULT get_allocatesBasePointer (   
   BOOL* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 `TRUE` 기본 포인터를 할당 하는 경우. 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 하 던 액세스 FPO\_DATA, 또는 때 프로그램 문자열을 반환 하는 코드에서이 속성을 사용 해야 해당 [IDiaFrameData::get\_program](../../debugger/debug-interface-access/idiaframedata-get-program.md) 방법입니다 `NULL`.  그렇지 않으면 프로그램 문자열 레지스터의 이전 값을 계산 하는 데 필요한 모든 정보가 들어 있습니다.  
  
## 참고 항목  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaFrameData::get\_program](../../debugger/debug-interface-access/idiaframedata-get-program.md)