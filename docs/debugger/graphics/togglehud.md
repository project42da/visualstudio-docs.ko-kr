---
title: ToggleHUD | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7261e01d-3c72-46ce-9fb3-5f33b2ddb901
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5bf1e27b9385257203653f3bff5241f6c3875373
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="togglehud"></a>ToggleHUD
그래픽 진단 설정/해제 *HUD* 오버레이 (헤드업 디스플레이)를 설정 하거나 해제 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
void ToggleHUD();  
```  
  
## <a name="remarks"></a>설명  
 그래픽 진단 HUD가 그래픽 진단에서 실행 중인 앱의 왼쪽 위에 표시됩니다. 그래픽 정보 캡처 및 호출 하 여 추가 된 메시지 및 응용 프로그램에 대 한 런타임 정보를 표시 된 [AddMessage](addmessage.md) 멤버 함수입니다.  
  
 HUD를 전환 하려면 그래픽 정보 캡처 적극적으로 사용할 필요가 없습니다-즉, 인스턴스를 통해 해제할 수 있습니다는 `VsgDbg` 클래스 이지만 [Init](init.md) 멤버 함수를 먼저 호출 필요가 없습니다.