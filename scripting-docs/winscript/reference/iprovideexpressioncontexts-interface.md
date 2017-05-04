---
title: "IProvideExpressionContexts 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IProvideExpressionContexts 인터페이스"
ms.assetid: e4c70f2c-7d86-4fdc-a1cb-f5a0bb8ed037
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IProvideExpressionContexts 인터페이스
특정 구성 요소에서 알려진 식 컨텍스트를 열거할 수가 있습니다.  스크립트 엔진은 일반적으로이 인터페이스를 구현 합니다.  
  
 프로세스 디버그 관리자 특정된 스레드와 관련 된 모든 전역 식 컨텍스트를 찾기 위해이 인터페이스를 사용 합니다.  
  
> [!NOTE]
>  이 인터페이스에서 관심 있는 스레드 내에서 호출 됩니다.  구현자까지 현재 스레드를 식별 하 고 해당 하는 열거자를 반환 하는 것.  
  
## 메서드  
 `IUnknown`에서 상속되는 메서드 외에 `IProvideExpressionContexts` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|---------|--------|  
|[IProvideExpressionContexts::EnumExpressionContexts](../../winscript/reference/iprovideexpressioncontexts-enumexpressioncontexts.md)|이 구성 요소에 의해 알려져 식 컨텍스트는 열거자를 반환 합니다.|