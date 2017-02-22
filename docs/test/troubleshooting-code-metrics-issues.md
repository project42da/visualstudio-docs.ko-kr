---
title: "코드 메트릭 문제 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2fdb995-4888-4246-85dc-7bacadd45968
caps.latest.revision: 4
caps.handback.revision: 4
author: "erickson-doug"
ms.author: "douge"
manager: "douge"
---
# 코드 메트릭 문제 해결
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

코드 메트릭을 수집할 때 다음과 같은 문제가 발생할 수 있습니다.  
  
-   [Visual Studio 2010에서 코드 복잡성 계산이 변경됨](#Changes_in_Visual_Studio_2010_code_complexity_calculations)  
  
##  <a name="Changes_in_Visual_Studio_2010_code_complexity_calculations"></a> Visual Studio 2010에서 코드 복잡성 계산이 변경됨  
 다음과 같은 경우 동일한 함수에 대해 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]에서 계산되는 코드 복잡성 메트릭과 이전 버전의 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]에서 계산되는 메트릭이 다를 수 있습니다.  
  
-   함수에 하나 이상의 catch 블록이 포함된 경우.  이전 버전의 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]에서는 catch 블록이 계산에 포함되지 않았습니다.  하지만 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]에서는 함수 복잡성에 각 catch 블록의 복잡성이 추가됩니다.  
  
-   함수에 switch\(VB의 경우 Select Case\) 문이 포함된 경우.  [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]과 이전 버전 간의 컴파일러 차이점으로 인해 제어 이동 case가 포함된 일부 switch 문의 경우 다른 MSIL 코드가 생성될 수 있습니다.  
  
## 참고 항목  
 [관리 코드의 복잡성 및 유지 관리 용이성 측정](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)