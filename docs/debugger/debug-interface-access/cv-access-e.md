---
title: CV_access_e | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_access_e enumeration
ms.assetid: 33c05d65-abb4-4800-a382-54a3805ea7b0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1cd11b7d72e84eb773a833414bb6c14716827cf9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="cvaccesse"></a>CV_access_e
표시 유형 (액세스 수준) 멤버 함수 및 변수의 범위를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
typedef enum CV_access_e {   
   CV_private   = 1,  
   CV_protected = 2,  
   CV_public    = 3  
} CV_access_e;  
```  
  
## <a name="elements"></a>요소  
 CV_private  
 멤버에 개인 액세스 합니다.  
  
 CV_protected  
 멤버 액세스를 보호 했습니다.  
  
 CV_public  
 멤버에 대 한 공용 액세스 합니다.  
  
## <a name="remarks"></a>설명  
 `friend` 액세스 지정자는 포함 되지 않습니다 여기 클래스의 전용 및 보호 된 요소에 액세스할 수 있는 멤버가 아닌 함수에서 일반적으로 사용 됩니다. 사용 하 여는 [idiasymbol:: Get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) 기호를 찾을 메서드의 `SymTagFriend` 액세스 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: cvconst.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasymbol:: Get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)   
 [IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)