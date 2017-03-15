---
title: "기호 형식의 클래스 계층 구조 | Microsoft Docs"
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
  - "기호[DIA SDK], 클래스 계층 구조"
ms.assetid: 0ccd6990-4654-44cd-a6f3-bdd82fe90f6c
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# 기호 형식의 클래스 계층 구조
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다음 표에서 클래스 계층 구조는 기호 형식을 설명합니다.  
  
## 기호 형식  
  
|기호 형식|설명|  
|-----------|--------|  
|[UDT](../../debugger/debug-interface-access/udt.md)|각 클래스, 구조체 및 공용 구조체를 나타내는 데 사용 되는 기호입니다.|  
|[열거형\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/enum-debug-interface-access-sdk.md)|열거 형식에 대 한 기호입니다.|  
|[PointerType](../../debugger/debug-interface-access/pointertype.md)|기호 포인터 형식입니다.|  
|[ArrayType](../../debugger/debug-interface-access/arraytype.md)|배열 형식에 대 한 기호입니다.|  
|[BaseType](../../debugger/debug-interface-access/basetype.md)|기본 형식에 대 한 기호|  
|[Typedef\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/typedef-debug-interface-access-sdk.md)|다른 형식 이름에 소개 하는 기호입니다.|  
|[BaseClass](../../debugger/debug-interface-access/baseclass.md)|사용자 정의 형식 \(UDT\)의 기본 클래스 각각에 대해 사용 되는 기호입니다.|  
|[Friend\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/friend-debug-interface-access-sdk.md)|Friend 클래스 및 friend 함수에 대 한 기호입니다.|  
|[FunctionType](../../debugger/debug-interface-access/functiontype.md)|기호 각 고유 함수 시그니처입니다.|  
|[FunctionArgType](../../debugger/debug-interface-access/functionargtype.md)|각 매개 변수는 함수에 대 한 기호입니다.|  
|[VTableShape](../../debugger/debug-interface-access/vtableshape.md)|가상 테이블의 크기에 대 한 기호입니다.|  
|[VTable](../../debugger/debug-interface-access/vtable.md)|기호는 가상 테이블입니다.|  
|[CustomType](../../debugger/debug-interface-access/customtype.md)|공급 업체에서 정의한 형식에 대 한 기호입니다.|  
|[ManagedType](../../debugger/debug-interface-access/managedtype.md)|메타 데이터에 정의 된 형식에 대 한 기호입니다.|  
|[크기](../../debugger/debug-interface-access/dimension.md)|배열 크기에 대 한 기호입니다.|  
  
> [!NOTE]
>  각 기호는 기호, 뿐만 아니라 기타 기호에 대 한 참조에 대 한 정보를 저장 하는 속성을 가질 수 있습니다.  이러한 속성은 개별 기호 항목에서 나열 됩니다.  
  
## 참고 항목  
 [CV\_access\_e 열거형](../../debugger/debug-interface-access/cv-access-e.md)   
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [기호 및 기호 태그](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)