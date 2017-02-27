---
title: "IDiaEnumSourceFiles::Next | Microsoft Docs"
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
  - "IDiaEnumSourceFiles::Next 메서드"
ms.assetid: 83bf6317-ff39-4c5c-8987-cba34e7a6983
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumSourceFiles::Next
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

열거 시퀀스에서 소스 파일의 지정 된 수를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT Next (   
   ULONG            celt,  
   IDiaSourceFile** rgelt,  
   ULONG*           pceltFetched  
);  
```  
  
#### 매개 변수  
 celt  
 \[in\] 수 원본 파일에서 검색 해야 하는 열거자입니다.  
  
 rgelt  
 \[out\]배열을 사용 하 여 입력 하는 것은 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) 원하는 원본 파일을 나타내는 개체입니다.  
  
 pceltFetched  
 \[out\] 소스 파일에서 반입 된 열거자를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 있는 경우 더 이상 원본 파일이 없습니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)