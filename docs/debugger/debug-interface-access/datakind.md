---
title: "DataKind | Microsoft Docs"
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
  - "DataKind 열거형"
ms.assetid: b64be708-22d6-4360-99e7-8f4e6b196de7
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# DataKind
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

데이터 값의 특정 범위를 나타냅니다.  
  
## 구문  
  
```cpp#  
enum DataKind {   
   DataIsUnknown,  
   DataIsLocal,  
   DataIsStaticLocal,  
   DataIsParam,  
   DataIsObjectPtr,  
   DataIsFileStatic,  
   DataIsGlobal,  
   DataIsMember,  
   DataIsStaticMember,  
   DataIsConstant  
};  
```  
  
## Elements  
 DataIsUnknown  
 데이터 기호를 확인할 수 없습니다.  
  
 DataIsLocal  
 데이터 항목이 로컬 변수입니다.  
  
 DataIsStaticLocal  
 데이터 항목은 정적 지역 변수입니다.  
  
 DataIsParam  
 데이터 항목의 형식 매개 변수입니다.  
  
 DataIsObjectPtr  
 데이터 항목 개체에 대 한 포인터입니다 \(`this`\).  
  
 DataIsFileStatic  
 데이터 항목 파일 범위 변수입니다.  
  
 DataIsGlobal  
 데이터 항목은 전역 변수입니다.  
  
 DataIsMember  
 데이터 항목 개체 멤버 변수입니다.  
  
 DataIsStaticMember  
 데이터 항목 클래스 정적 변수입니다.  
  
 DataIsConstant  
 데이터 항목에는 상수 값입니다.  
  
## 설명  
 이 열거형의 값으로 반환 되는 [IDiaSymbol::get\_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md) 방법입니다.  
  
## 요구 사항  
 헤더: cvconst.h  
  
## 참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get\_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)