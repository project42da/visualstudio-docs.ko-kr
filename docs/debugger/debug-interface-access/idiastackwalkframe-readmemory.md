---
title: "IDiaStackWalkFrame::readMemory | Microsoft Docs"
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
  - "IDiaStackWalkFrame::readMemory 메서드"
ms.assetid: 7ab0b525-a5a7-4692-acad-e8c00fa9ab9a
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaStackWalkFrame::readMemory
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이미지에서 메모리를 읽습니다.  
  
## 구문  
  
```cpp#  
HRESULT readMemory (   
   MemoryTypeEnum type,  
   ULONGLONG va,  
   DWORD     cbData,  
   DWORD*    pcbData,  
   BYTE      data[]  
);  
```  
  
#### 매개 변수  
 `type`  
 \[in\] 중 하나는 [MemoryTypeEnum 열거형](../../debugger/debug-interface-access/memorytypeenum.md) 메모리 액세스의 종류를 지정 하는 열거형 값입니다.  
  
 `va`  
 \[in\] 가상 주소 이미지 읽기를 시작할 위치입니다.  
  
 `cbData`  
 \[in\] 바이트에서 데이터 버퍼의 크기입니다.  
  
 `pcbData`  
 \[out\] 반환 된 바이트 수를 반환 합니다.  경우 `data` 입니다 `NULL`, 다음 `pcbData` 총 사용 가능한 데이터의 바이트 수를 포함 합니다.  
  
 `data`  
 \[out\] 데이터의 지정 된 위치에서에 입력할 수 있는 버퍼입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)