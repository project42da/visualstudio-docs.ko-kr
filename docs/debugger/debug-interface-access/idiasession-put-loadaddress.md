---
title: 'Idiasession:: Put_loadaddress | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSession::put_loadAddress method
ms.assetid: b157b245-1ea0-4b80-8962-d8b278dbc742
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f4721ee818c4dc75d883c7accd2faa162521de13
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasessionputloadaddress"></a>IDiaSession::put_loadAddress
이 기호 저장소의 기호에 해당 하는 실행 파일에 대 한 부하 주소를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT put_loadAddress (   
   ULONGLONG NewVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `NewVal`  
 [in] 실행 파일에 대 한 주소를 로드 합니다.  
  
## <a name="remarks"></a>설명  
 기호 가상 주소 VA 속성은이 메서드의 값을 사용 하 여 계산 됩니다. 가상 주소에는이 속성은 0이 아닌 값 설정 하지 않으면 계산 되지 않습니다.  
  
> [!NOTE]
>  가져오는 경우이 메서드를 호출 해야 합니다는 [IDiaSession](../../debugger/debug-interface-access/idiasession.md) 개체 및 기호에서 모든 가상 속성을 사용 해야 할 경우 개체를 사용 하기 전에.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)