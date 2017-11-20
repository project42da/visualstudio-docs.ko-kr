---
title: 'Idiastackwalkframe:: Put_registervalue | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackWalkFrame::put_registerValue method
ms.assetid: 2d8b79b6-7240-43fe-b24e-e4ff3e2c15b0
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f04710993efc9c1b0d0508a428c55013208f13a2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiastackwalkframeputregistervalue"></a>IDiaStackWalkFrame::put_registerValue
레지스터의 값을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT put_registerValue (   
   DWORD     index,  
   ULONGLONG NewVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `index`  
 [in] 값은 [CV_HREG_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md) 에 쓸 수는 레지스터를 지정 하는 열거형입니다.  
  
 `NewVal`  
 [in] 새 레지스터 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)   
 [CV_HREG_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md)