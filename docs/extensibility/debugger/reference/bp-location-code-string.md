---
title: BP_LOCATION_CODE_STRING | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BP_LOCATION_CODE_STRING
helpviewer_keywords: BP_LOCATION_CODE_STRING structure
ms.assetid: a4cd71c6-5052-45fe-907b-ebc6ca1df2e4
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2c49962892cdc0c83d8e3b7ae22ca0c4ee7f13d6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bplocationcodestring"></a>BP_LOCATION_CODE_STRING
사용자는 통합된 개발 환경 (IDE)에서 입력할 수 있는 문자열을 기반으로 코드 중단점을 설정 하기 위한 사용.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _BP_LOCATION_CODE_STRING {   
   BSTR bstrContext;  
   BSTR bstrCodeExpr;  
} BP_LOCATION_CODE_STRING;  
```  
  
## <a name="members"></a>멤버  
 `bstrContext`  
 코드 내에서 중단점 호출 스택에 보듯이 메서드 또는 함수 이름, 일반적으로의 컨텍스트.  
  
 `bstrCodeExpr`  
 사용자에 코드 중단점을 설명 하기 위해 입력 하는 문자열입니다.  
  
## <a name="remarks"></a>설명  
 이 구조는의 구성원은 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) 공용 구조체의 일부로 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)