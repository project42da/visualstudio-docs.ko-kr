---
title: "ISetNextStatement 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b570c2e0-a173-4f14-97d8-f39465753115
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bdd71a427a8ef2c57684eef75a044d0cedf42415
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="isetnextstatement-interface"></a>ISetNextStatement 인터페이스
이 인터페이스는 프로세스를 디버깅 관리자 현재 문을 업데이트를 허용 하도록 인터프리터에 의해 구현 됩니다. 스택 프레임 개체에서 구현 하 고는 PDM QueryInterface 통해이 인터페이스를 가져옵니다.  
  
 인터페이스는 다음 문을 실행 하도록 결정 하는 실행 위치를 설정 하는 데 도움이 되는 메서드를 제공 합니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `ISetNextStatement` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ISetNextStatement::CanSetNextStatement](../../winscript/reference/isetnextstatement-cansetnextstatement.md)|지정된 된 위치에 실행 위치를 설정할 수 있는지 여부를 결정 합니다.|  
|[ISetNextStatement::SetNextStatement](../../winscript/reference/isetnextstatement-setnextstatement.md)|지정 된 위치에 실행 위치를 설정합니다.|