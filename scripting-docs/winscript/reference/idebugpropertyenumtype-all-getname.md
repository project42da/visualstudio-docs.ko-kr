---
title: IDebugPropertyEnumType_All::GetName | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugPropertyEnumType_All.GetName
apilocation: scrobj.dll
helpviewer_keywords: IDebugPropertyEnumType_All::GetName
ms.assetid: 24bbe4d5-4263-48d0-8e8d-bff957ffcad2
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 49b90938630fa96ca91f3346a37a7147ec2b90e7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugpropertyenumtypeallgetname"></a>IDebugPropertyEnumType_All::GetName
이름을 포함 하는 BSTR을 반환 된 `EnumType`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetName(  
   BSTR*  pname  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pname`  
 [out] 이름을 포함 하는 BSTR는 `EnumType`합니다.  
  
## <a name="return-value"></a>반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPropertyEnumType_All 인터페이스](../../winscript/reference/idebugpropertyenumtype-all-interface.md)