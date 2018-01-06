---
title: UdtKind | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: UdtKind enumeration
ms.assetid: 400b59b9-373c-42cb-aae1-570494214328
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ba00f8e257e1ada0903e17b231f668a4eb30052a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
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