---
title: "DLL 응용 프로그램 클라이언트가 너무 많습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID47"
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# DLL 응용 프로그램 클라이언트가 너무 많습니다.
[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에 대한 DLL\(동적 연결 라이브러리\)은 제한된 수의 호스트 응용 프로그램 액세스만 허용할 수 있습니다. 사용자 응용 프로그램 및 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 호스트인 다른 응용 프로그램\(일부는 사용자 응용 프로그램에서 액세스할 수 있음\)이 동시에 모두 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] DDL에 액세스하려고 합니다.  
  
### 이 오류를 해결하려면  
  
-   [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에 액세스하는 열려 있는 응용 프로그램 수를 줄입니다.  
  
## 참고 항목  
 [Error Types](/dotnet/visual-basic/programming-guide/language-features/error-types)