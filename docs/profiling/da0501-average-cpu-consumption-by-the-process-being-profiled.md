---
title: "DA0501: 프로파일링 중인 프로세스의 평균 CPU 사용 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DA0501
- vs.performance.DA0501
- vs.performance.501
ms.assetid: b01946b4-75e3-47d5-a1a1-cebfae66a3af
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 2269ea4c58703cf5f2c4d8516e14cb40b342c958

---
# <a name="da0501-average-cpu-consumption-by-the-process-being-profiled"></a>DA0501: 프로파일링 중인 프로세스의 평균 CPU 사용
|||  
|-|-|  
|규칙 ID|DA501|  
|범주|리소스 모니터링|  
|프로파일링 방법|모두|  
|메시지|프로파일링되고 있는 프로세스의 평균 CPU 사용입니다.|  
|규칙 유형|정보|  
  
 샘플링, .NET 메모리 또는 리소스 경합 방법을 사용하여 프로파일링할 경우 이 규칙을 트리거하려면 10개 이상의 샘플을 수집해야 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 이 메시지는 응용 프로그램에서 명령을 실행할 때 프로세서가 사용 중이었던 시간의 백분율을 보고합니다. 보고된 값은 프로파일링되는 프로세스가 활성 상태였던 모든 측정 간격에 대한 평균입니다. 프로세서가 두 개 이상 있는 컴퓨터에서 이 값은 100%보다 클 수 있습니다.  
  
## <a name="how-to-use-rule-data"></a>규칙 데이터를 사용하는 방법  
 규칙 값을 사용하여 프로그램의 여러 가지 버전이나 빌드에 대한 성능을 비교하거나 여러 가지 테스트 시나리오에서 응용 프로그램의 성능을 파악합니다.


<!--HONumber=Feb17_HO4-->

