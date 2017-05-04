---
title: "ISetNextStatement 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b570c2e0-a173-4f14-97d8-f39465753115
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# ISetNextStatement 인터페이스
이 인터페이스는 인터프리터가 현재 문을 업데이트 프로세스 디버그 관리자 허용 하도록 구현 됩니다.  스택 프레임 개체에서 구현 하 고이 인터페이스를 통해 QueryInterface PDM을 가져옵니다.  
  
 인터페이스 결정 실행할 다음 문을 실행 위치를 설정 하는 데 유용한 방법을 제공 합니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `ISetNextStatement` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[ISetNextStatement::CanSetNextStatement](../../winscript/reference/isetnextstatement-cansetnextstatement.md)|지정한 위치에 실행 위치를 설정할 수 있는지 여부를 결정 합니다.|  
|[ISetNextStatement::SetNextStatement](../../winscript/reference/isetnextstatement-setnextstatement.md)|실행 위치를 지정 된 위치로 설정합니다.|