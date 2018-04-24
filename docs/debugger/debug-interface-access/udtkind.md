---
title: UdtKind | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- UdtKind enumeration
ms.assetid: 400b59b9-373c-42cb-aae1-570494214328
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b95d8bfeda0cd8d5efdaab6d0c2fd13a34c8407c
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="udtkind"></a>UdtKind
다양 한 사용자 정의 형식 (UDT)에 대해 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
enum UdtKind {   
   UdtStruct,  
   UdtClass,  
   UdtUnion,  
   UdtInterface  
};  
```  
  
## <a name="elements"></a>요소  
 UdtStruct  
 UDT는 구조체입니다.  
  
 UdtClass  
 UDT 클래스가 생성 됩니다.  
  
 UdtUnion  
 UDT는 공용 구조체입니다.  
  
 UdtInterface  
 UDT는 인터페이스입니다.  
  
## <a name="remarks"></a>설명  
 이 열거형의 값을 반환 된 [idiasymbol:: Get_udtkind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: cvconst.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)