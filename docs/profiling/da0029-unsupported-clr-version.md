---
title: 'DA0029: 지원되지 않는 CLR 버전 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.29
- vs.performance.rules.DA0029
helpviewer_keywords:
- vs.performance.29
- vs.performance.DA0029
- vs.performance.rules.DA0029
ms.assetid: 76247259-c6f3-44c4-b3f9-d8dac16b5e0d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ad41dc48303fa836e4c15f0e450b3fade60ff646
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="da0029-unsupported-clr-version"></a>DA0029: 지원되지 않는 CLR 버전
|||  
|-|-|  
|규칙 ID|DA0029|  
|범주|프로파일링 도구 사용|  
|프로파일링 방법|명령줄에서 프로파일링|  
|메시지|지원되지 않는 CLR 버전이 수집하는 동안 발견되었습니다. 관리되는 기호가 제대로 확인되지 않을 수 있습니다.|  
|규칙 유형|정보.|  
  
## <a name="cause"></a>원인  
 프로파일링 도구에서 지원되지 않는 [!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)]을(를) 사용하는 응용 프로그램 프로파일링하려고 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 이 경고는 프로파일링 도구가 응용 프로그램에서 실행되는 관리되는 코드에 대한 기호를 확인할 수 없기 때문에 발생합니다. 프로파일링 도구는 [!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)]을(를) 실행하는 응용 프로그램에 대한 관리되는 코드 기호를 확인할 수 없습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 없음