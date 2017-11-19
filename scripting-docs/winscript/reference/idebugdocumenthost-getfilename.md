---
title: IDebugDocumentHost::GetFileName | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugDocumentHost.GetFileName
apilocation: scrobj.dll
helpviewer_keywords: IDebugDocumentHost::GetFileName
ms.assetid: b814a848-8a3d-468d-9282-c5c0354b22a1
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 909c431a389a2589d48b6228534b16675ea41383
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenthostgetfilename"></a>IDebugDocumentHost::GetFileName
경로 정보 없이 문서의 이름을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetFileName(  
   BSTR*  pbstrShortName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrShortName`  
 [out] 문서의 짧은 이름을 포함 하는 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 경로 정보 없이 문서의 약식 이름을 반환합니다. 약식 이름을 일반적으로 상황에서 사용 됩니다와 같은 **다른 이름으로 저장...**  대화 상자.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentHost 인터페이스](../../winscript/reference/idebugdocumenthost-interface.md)