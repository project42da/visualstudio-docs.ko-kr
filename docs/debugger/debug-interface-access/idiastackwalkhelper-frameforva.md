---
title: IDiaStackWalkHelper::frameForVA | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackWalkHelper2::frameForVA method
ms.assetid: f35fc61b-f8dd-473a-b583-82c304059422
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f2ea7272c3a01680e1776c15f945e2d10ed973a9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiastackwalkhelperframeforva"></a>IDiaStackWalkHelper::frameForVA
지정된 된 가상 주소 포함 된 스택 프레임을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT frameForVA(   
   ULONGLONG        va,  
   IDiaFrameData**  ppFrame  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `va`  
 [in] 프레임 데이터에 대 한 가상 주소입니다.  
  
 `ppFrame`  
 [out] [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) 지정된 된 주소에서 스택 프레임을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)