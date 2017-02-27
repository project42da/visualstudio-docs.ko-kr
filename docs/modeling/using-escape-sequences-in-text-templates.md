---
title: "텍스트 템플릿에서 이스케이프 시퀀스 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "텍스트 템플릿, 이스케이프 시퀀스"
ms.assetid: 36fff542-2f42-460f-a2d5-03fc76817f3b
caps.latest.revision: 29
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 29
---
# 텍스트 템플릿에서 이스케이프 시퀀스 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

텍스트 템플릿에서 이스케이프 시퀀스를 사용하여 텍스트 템플릿 태그를 생성할 수 있으며 C\# 코드에서 제어 문자와 따옴표를 이스케이프할 수 있습니다.  
  
 표준 코드 블록의 여는 태그와 닫는 태그를 출력 파일로 인쇄하려면 다음과 같이 태그를 이스케이프합니다.  
  
```  
\<# ... \#>  
```  
  
 다른 텍스트 템플릿 지시문과 코드 블록 태그도 동일하게 처리할 수 있습니다.  
  
 텍스트 블록에 텍스트 템플릿 태그를 이스케이프하는 데 사용되는 문자열이 포함되어 있으면 다음 이스케이프 시퀀스를 사용할 수 있습니다.  
  
-   텍스트 템플릿 태그 앞에 짝수 개의 이스케이프 문자\(\\\)가 있는 경우 템플릿 파서는 이스케이프 문자의 절반을 포함하고 해당 시퀀스를 텍스트 템플릿 태그로 포함합니다.  예를 들어, 텍스트 템플릿에 이스케이프 문자가 4개 있으면 생성된 파일에 "\\" 문자가 두 개 있습니다.  
  
-   텍스트 템플릿 태그 앞에 홀수 개의 이스케이프 문자\(\\\)가 있는 경우 템플릿 파서는 "\\" 문자의 절반과 태그 자체\(\<\# 또는 \#\>\)를 포함합니다.  이 태그는 텍스트 템플릿 태그로 간주되지 않습니다.  
  
-   이스케이프 문자\(\\\)가 시퀀스에서 제어 문자나 따옴표를 이스케이프하는\(C\#에만 해당\) 곳이 아닌 위치에 나타나는 경우 해당 문자가 직접 출력됩니다.  
  
## 참고 항목  
 [방법: 이스케이프 시퀀스를 사용하여 템플릿에서 템플릿 생성](../modeling/how-to-generate-templates-from-templates-by-using-escape-sequences.md)