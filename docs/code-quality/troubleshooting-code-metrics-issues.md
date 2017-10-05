---
title: "코드 메트릭 문제 해결 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2fdb995-4888-4246-85dc-7bacadd45968
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: ea1e787c1d509123a650cf2bd20e5fa8bffd5b4e
ms.openlocfilehash: 9f3f41548412d84cd1219aae45b7c87ea5383de9
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="troubleshooting-code-metrics-issues"></a>코드 메트릭 문제 해결
코드 메트릭을 수집할 때 다음 문제 중 일부를 발생할 수 있습니다.  
  
-   [Visual Studio 2010 코드 복잡성 계산에 대 한 변경 내용](#Changes_in_Visual_Studio_2010_code_complexity_calculations)  
  
##  <a name="Changes_in_Visual_Studio_2010_code_complexity_calculations"></a>Visual Studio 2010 코드 복잡성 계산에 대 한 변경 내용  
 동일한 기능에 대 한 코드 복잡성 메트릭은에 계산 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] 수와에서 다를 이전 버전의에서 계산 하는 메트릭을 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 다음과 같은 상황에서:  
  
-   함수에 포함 되어 하나 이상의 catch 블록 또는 합니다. 이전 버전의 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], catch 블록은 계산에 포함 되지 않았습니다. [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)], 각 catch 블록의 복잡성은 복잡 한 함수에 추가 됩니다.  
  
-   함수 (VB의 경우 선택) switch 문을 포함합니다. 컴파일러 간의 차이로 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] 이전 버전 fall 통해 사례를 포함 하는 일부 switch 문의 다른 MSIL 코드를 생성할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리 코드의 복잡성 및 유지 관리 용이성 측정](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)
