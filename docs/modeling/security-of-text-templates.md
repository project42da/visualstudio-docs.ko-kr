---
title: "텍스트 템플릿 보안 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "텍스트 템플릿, 보안"
ms.assetid: 567a2383-7d43-4acc-af4a-cd70b7a0151e
caps.latest.revision: 23
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 23
---
# 텍스트 템플릿 보안
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

텍스트 템플릿에는 다음과 같은 보안 문제가 있습니다.  
  
-   텍스트 템플릿에 임의의 코드가 삽입될 수 있습니다.  
  
-   호스트에서 지시문 프로세서를 찾는 데 사용하는 메커니즘이 안전하지 않은 경우 악의적인 지시문 프로세서가 실행될 수 있습니다.  
  
## 임의의 코드  
 템플릿을 작성할 때 \<\# \#\> 태그 안에 임의의 코드를 넣을 수 있습니다.  이에 따라 임의의 코드가 텍스트 템플릿 내에서 실행될 수 있습니다.  
  
 신뢰할 수 있는 소스에서 템플릿을 얻어야 합니다.  신뢰할 수 있는 소스에서 제공되지 않은 템플릿을 실행하지 않도록 응용 프로그램의 최종 사용자에게 경고해야 합니다.  
  
## 악의적인 지시문 프로세서  
 텍스트 템플릿 엔진은 변환 호스트 및 하나 이상의 지시문 프로세서와 상호 작용하여 템플릿 텍스트를 출력 파일로 변환합니다.  자세한 내용은 [텍스트 템플릿 변환 프로세스](../modeling/the-text-template-transformation-process.md)를 참조하십시오.  
  
 호스트에서 지시문 프로세서를 찾는 데 사용하는 메커니즘이 안전하지 않은 경우 악의적인 지시문 프로세서를 실행할 위험이 있습니다.  악의적인 지시문 프로세서는 템플릿이 실행될 때 `FullTrust` 모드에서 실행되는 코드를 제공할 수 있습니다.  사용자 지정 텍스트 템플릿 변환 호스트를 만드는 경우 레지스트리와 같은 보안 메커니즘을 사용하여 엔진이 지시문 프로세서를 찾도록 해야 합니다.