---
title: "텍스트 템플릿에서 이스케이프 시퀀스를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, escape sequences
ms.assetid: 36fff542-2f42-460f-a2d5-03fc76817f3b
caps.latest.revision: "29"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: fdf062c9b33dd4a160f54bba83991a3cdda7f0d1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="using-escape-sequences-in-text-templates"></a>텍스트 템플릿에서 이스케이프 시퀀스 사용
텍스트 템플릿에서 텍스트 템플릿 태그를 생성 하 고 (C# 코드에만 해당)에서 이스케이프 시퀀스를 사용할 수 인용 부호 및 이스케이프 제어 문자.  
  
 출력 파일에 표준 코드 블록에 대 한 괄호와 닫는 태그를 인쇄 하려면 태그를 다음과 같이 이스케이프:  
  
```  
\<# ... \#>  
```  
  
 다른 텍스트 템플릿 지시문 및 코드 블록 태그와 동일 하 게 수행할 수 있습니다.  
  
 텍스트 블록 이스케이프 텍스트 템플릿 태그를 사용 하는 문자열을 포함 하는 경우 다음과 같은 이스케이프 시퀀스를 사용할 수 있습니다.  
  
-   텍스트 템플릿 태그 이스케이프 수가 짝수인 경우 앞 (\\) 문자는 서식 파일 파서 됩니다 절반 이스케이프 문자를 포함 하 고 텍스트 템플릿 태그도 시퀀스를 포함 합니다. 예를 들어 텍스트 템플릿에서 이스케이프 문자가 4 개 있는 경우 됩니다 두 "\\" 생성된 된 파일에는 문자입니다.  
  
-   텍스트 템플릿 태그 이스케이프 수가 홀수인 경우 앞 (\\) 문자를 서식 파일 파서가 포함 됩니다의 절반는 "\\" 태그 자체 문자 (\<# 또는 #>). 태그는 텍스트 템플릿 태그으로 간주 되지 않습니다.  
  
-   이스케이프 하는 경우 (\\)에서 제어 문자 또는 (에서 C#에 해당)는 따옴표를 이스케이프 위치 이외의 모든 시퀀스의 다른 곳에 표시 되는 문자의 문자 직접 출력 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 이스케이프 시퀀스를 사용하여 템플릿에서 템플릿 생성](../modeling/how-to-generate-templates-from-templates-by-using-escape-sequences.md)