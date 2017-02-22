---
title: "IDiaSession::findFileById | Microsoft Docs"
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
  - "IDiaSession::findFileById 메서드"
ms.assetid: 710efe04-78b5-4f3e-a1d8-f9b069063503
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSession::findFileById
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

원본 파일에서 원본 파일 식별자를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT findFileById (   
   DWORD            uniqueId,  
   IDiaSourceFile** ppResult  
);  
```  
  
#### 매개 변수  
 `uniqueId`  
 \[in\] 소스 파일 식별자를 지정합니다.  
  
 `ppResult`  
 \[out\] 반환 된 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) 원본 파일을 나타내는 개체를 검색 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 원본 파일 식별자가 모든 소스 파일을 고유 하 게 만들기 DIA SDK를 내부적으로 사용 되는 고유 값입니다.  일반적으로이 메서드는 DIA SDK를 내부적으로 사용 됩니다.  
  
## 참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSession::findFile](../../debugger/debug-interface-access/idiasession-findfile.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)