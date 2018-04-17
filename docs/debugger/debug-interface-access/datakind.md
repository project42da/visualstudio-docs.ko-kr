---
title: DataKind | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DataKind enumeration
ms.assetid: b64be708-22d6-4360-99e7-8f4e6b196de7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 508058a85d60645fca5e50bc1e6c456da7df7b26
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="datakind"></a>DataKind
데이터 값의 특정 범위를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
enum DataKind {   
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
  
## <a name="elements"></a>요소  
 DataIsUnknown  
 데이터 기호를 확인할 수 없습니다.  
  
 DataIsLocal  
 데이터 항목에는 지역 변수입니다.  
  
 DataIsStaticLocal  
 데이터 항목에는 정적 지역 변수입니다.  
  
 DataIsParam  
 데이터 항목은 형식 매개 변수입니다.  
  
 DataIsObjectPtr  
 데이터 항목에는 개체 포인터입니다 (`this`).  
  
 DataIsFileStatic  
 데이터 항목에는 파일 범위 변수입니다.  
  
 DataIsGlobal  
 데이터 항목에는 전역 변수입니다.  
  
 DataIsMember  
 데이터 항목은 개체 멤버 변수입니다.  
  
 DataIsStaticMember  
 데이터 항목에 클래스 정적 변수입니다.  
  
 DataIsConstant  
 데이터 항목은 상수 값입니다.  
  
## <a name="remarks"></a>설명  
 이 열거형의 값을 반환 된 [idiasymbol:: Get_datakind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: cvconst.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)