---
title: "IDiaStackFrame::get_rawLVarInstanceValue | Microsoft Docs"
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
  - "IDiaStackFrame::get_rawLVarInstanceValue 메서드"
ms.assetid: ce526259-85a6-475b-9274-0b3a21d95db2
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IDiaStackFrame::get_rawLVarInstanceValue
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 메서드는 지정 된 지역 변수의 값 원시 바이트로 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_rawLVarInstanceValue(  
   IDiaLVarInstance* pInstance,  
   DWORD             cbDataMax,  
   DWORD*            pcbData,  
   BYTE*             pbData  
);  
```  
  
#### 매개 변수  
 `pInstance`  
 \[in\] `IDiaLVarInstance` 인스턴스 값에 대 한 지역 변수를 나타내는 개체입니다.  
  
 `cbDataMax`  
 \[in\] 최대 버퍼의 바이트 수로를 가리키는 `pbData`.  이 최대 8 바이트 수 있습니다 \(`sizeof(ULONGLONG)`\).  
  
 `pcbData`  
 \[out\] 실제 버퍼에 저장 되는 바이트 수를 반환 합니다.  
  
 `pbData`  
 \[out\] 데이터를 사용 하 여 데이터를 입력할 수 있는 버퍼입니다.  이는 `NULL`일 수 없습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)