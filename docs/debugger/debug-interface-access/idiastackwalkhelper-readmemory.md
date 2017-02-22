---
title: "IDiaStackWalkHelper::readMemory | Microsoft Docs"
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
  - "IDiaStackWalkHelper2::readMemory 메서드"
ms.assetid: e1eb90aa-49b7-476c-9e70-7e8f08994cbe
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaStackWalkHelper::readMemory
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

데이터 블록의 메모리에 있는 실행 파일의 이미지를 읽습니다.  
  
## 구문  
  
```cpp#  
HRESULT readMemory(   
   enum MemoryTypeEnum type,  
   ULONGLONG           va,  
   DWORD               cbData,  
   DWORD*              pcbData,  
   BYTE*               pbData  
);  
```  
  
#### 매개 변수  
 `type`  
 \[in\] 값은 [MemoryTypeEnum 열거형](../../debugger/debug-interface-access/memorytypeenum.md) 을 읽기 위해 메모리의 종류를 지정 하는 열거형입니다.  
  
 va  
 \[in\] 이미지에서 읽기 시작할 가상 주소입니다.  
  
 `cbData`  
 \[in\] 데이터 버퍼의 바이트 크기입니다.  
  
 `pcbData`  
 \[out\] 실제로 읽은 바이트 수를 반환 합니다.  경우 `pbData` 입니다 `NULL`,이 총 사용 가능한 데이터의 바이트 수입니다.  
  
 `pbData`  
 \[in, out\] 읽기 메모리 사용 하 여 채워진 버퍼입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [MemoryTypeEnum 열거형](../../debugger/debug-interface-access/memorytypeenum.md)