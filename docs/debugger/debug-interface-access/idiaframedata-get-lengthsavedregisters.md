---
title: "IDiaFrameData::get_lengthSavedRegisters | Microsoft Docs"
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
  - "IDiaFrameData::get_lengthSavedRegisters 메서드"
ms.assetid: dfda4e91-9bfa-4b9d-9133-b73015bfa4d5
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaFrameData::get_lengthSavedRegisters
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

저장 된 레지스터는 스택에 푸시된 바이트 수를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_lengthSavedRegisters (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 저장 된 레지스터의 바이트 수를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드에서 반환 된 값을 해석 프로그램 문자열을 일반적으로 사용 됩니다 \(참조는 [IDiaFrameData::get\_program](../../debugger/debug-interface-access/idiaframedata-get-program.md) 메서드를 정의 하는 프로그램 문자열\).  
  
## 참고 항목  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaFrameData::get\_program](../../debugger/debug-interface-access/idiaframedata-get-program.md)