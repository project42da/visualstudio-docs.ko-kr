---
title: "이 컨텍스트에서는 &#39;Global&#39;을 사용할 수 없습니다. 식별자가 필요합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36001"
  - "bc36001"
helpviewer_keywords: 
  - "BC36001"
ms.assetid: d515daa2-f53d-424c-81fd-e9c4b12f331b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 이 컨텍스트에서는 &#39;Global&#39;을 사용할 수 없습니다. 식별자가 필요합니다.
`Global` 키워드가 허용되지 않은 문에서 사용됩니다.  
  
 `Global` 키워드를 사용하면 코드를 컴파일할 네임스페이스 계층 구조 외부에서 정의된 네임스페이스에 액세스할 수 있습니다.`Global`은 .NET Framework 클래스 라이브러리의 가장 바깥쪽 네임스페이스 수준에서 정규화된 경로를 시작합니다.[Global \- 삭제](http://msdn.microsoft.com/ko-kr/18c8ba14-40f6-4978-8096-6a5852324635)의 그림을 참조하세요.  
  
 `Imports` 및 `Namespace` 등의 특정 문은 코드를 컴파일할 네임스페이스에 종속되지 않습니다.<xref:System> 또는 <xref:Microsoft.VisualBasic>과 같이 루트 수준 네임스페이스에서 시작하는 정규화된 경로가 필요합니다. 이러한 문에서 `Global` 키워드는 불필요하며 허용되지 않습니다.  
  
 **오류 ID:** BC36001  
  
### 이 오류를 해결하려면  
  
-   문에서 `Global` 키워드를 제거합니다. 필요하지 않습니다.  
  
## 참고 항목  
 [Global \- 삭제](http://msdn.microsoft.com/ko-kr/18c8ba14-40f6-4978-8096-6a5852324635)   
 [Imports Statement \(.NET Namespace and Type\)](/dotnet/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type)   
 [Namespace Statement](/dotnet/visual-basic/language-reference/statements/namespace-statement)   
 [References and the Imports Statement](/dotnet/visual-basic/programming-guide/program-structure/references-and-the-imports-statement)