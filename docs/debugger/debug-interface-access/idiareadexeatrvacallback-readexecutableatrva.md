---
title: "IDiaReadExeAtRVACallback::ReadExecutableAtRVA | Microsoft Docs"
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
  - "IDiaReadExeAtRVACallback::ReadExecutableAtRVA 메서드"
ms.assetid: 3c1e965f-8f05-41a8-86d8-01830b2377c9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaReadExeAtRVACallback::ReadExecutableAtRVA
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정한 상대 가상 주소 \(RVA\) 실행 파일을 시작 하는 바이트 수를 지정 된 수를 읽습니다.  
  
## 구문  
  
```cpp#  
HRESULT ReadExecutableAtRVA (   
   DWORD  relativeVirtualAddress,  
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### 매개 변수  
 `relativeVirtualAddress`  
 \[in\] 읽기를 시작할 실행 파일의 RVA입니다.  
  
 `cbData`  
 \[in\] 읽을 바이트의 수입니다.  
  
 `pcbData`  
 \[out\] 읽은 바이트 수를 반환 합니다.  
  
 `data[]`  
 \[in, out\] 파일에서 읽은 바이트 사용 하 여 입력 되는 배열입니다.  
  
## 설명  
 DIA 지원 코드 데이터 바이트 상대 가상 주소를 사용 하 여 실행 파일에서 로드 하 여이 메서드가 호출 됩니다.  지원에이 메서드가 호출 되는 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 메서드.  
  
## 참고 항목  
 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)