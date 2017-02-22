---
title: "코드 조각 문제 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IntelliSense 코드 조각, 문제 해결"
  - "IntelliSense 코드 조각 문제 해결"
  - "Visual Basic 문제 해결, IntelliSense 코드 조각"
ms.assetid: 7b6dd40e-2f78-4b50-8e68-41fac1bcb81e
caps.latest.revision: 17
caps.handback.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 코드 조각 문제 해결
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

IntelliSense 코드 조각 문제는 코드 조각 파일이 손상되었거나 코드 조각 파일에 잘못된 내용이 있는 경우에 일반적으로 발생합니다.  
  
## 일반적인 문제  
  
### 코드 조각 파일 탐색기에서 Visual Studio 원본 파일을 끌 수 없습니다.  
  
-   코드 조각 파일의 XML이 손상되었을 수 있습니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 **XML 편집기**에서 XML 구조 문제를 찾을 수 있습니다.  
  
-   코드 조각 파일이 조각 파일 스키마에 맞지 않을 수 있습니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 **XML 편집기**에서 XML 구조 문제를 찾을 수 있습니다.  
  
### 코드에 강조 표시되지 않는 컴파일러 오류가 있습니다.  
  
-   프로젝트 참조가 없을 수 있습니다.  코드 조각에 대한 설명서를 살펴봅니다.  컴퓨터에 참조가 없는 경우 참조를 설치해야 합니다.  코드 조각을 삽입하여 프로젝트에 필요한 참조를 추가해야 합니다.  코드 조각에 참조 정보가 없는 경우 코드 조각 생성자에 오류가 보고될 수 있습니다.  
  
-   변수가 정의되어 있지 않을 수 있습니다.  코드 조각에서 정의되지 않은 변수는 강조 표시되어야 합니다.  그렇지 않은 경우 코드 조각 생성자에 오류가 보고될 수 있습니다.  
  
## 참고 항목  
 [코드 조각](../ide/code-snippets.md)