---
title: "IDiaReadExeAtOffsetCallback::ReadExecutableAt | Microsoft Docs"
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
  - "IDiaReadExeAtOffsetCallback::ReadExecutableAt 메서드"
ms.assetid: 30b1cef0-b366-4712-8e89-d21f640964f8
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaReadExeAtOffsetCallback::ReadExecutableAt
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정한 실행 파일의 지정 된 오프셋에서 시작 하는 바이트 수를 읽습니다.  
  
## 구문  
  
```cpp#  
HRESULT ReadExecutableAt (   
   DWORDLONG fileOffset,  
   DWORD     cbData,  
   DWORD*    pcbData,  
   BYTE      data[]  
);  
```  
  
#### 매개 변수  
 fileOffset  
 \[in\] 읽기를 시작할 실행 파일의 오프셋입니다.  
  
 사용  
 \[in\] 읽을 바이트의 수입니다.  
  
 pcbData  
 \[out\] 읽은 바이트 수를 반환 합니다.  
  
 데이터\]  
 \[in, out\] 파일에서 읽은 바이트 사용 하 여 입력 되는 배열입니다.  
  
## 설명  
 DIA 지원 코드 데이터 바이트는 절대 파일 오프셋을 사용 하 여 실행 파일에서 로드 하 여이 메서드가 호출 됩니다.  지원에이 메서드가 호출 되는 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 메서드.  
  
## 참고 항목  
 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)