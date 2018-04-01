---
title: '방법: using __analysis_assume 사용 하 여 추가 코드 정보를 지정 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- __analysis_assume
helpviewer_keywords:
- __analysis_assume
ms.assetid: 51205d97-4084-4cf4-a5ed-3eeaf67deb1b
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 72b72ce474a24d77b3b40513c2e69fb5ab4aea59
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-additional-code-information-by-using-analysisassume"></a>How to: Using __analysis_assume 사용하여 추가 코드 정보 지정
C/c + + 코드를 분석 프로세스는 데 도움이 되 고 줄어들지만 경고에 대 한 코드 분석 도구에 대 한 힌트를 제공할 수 있습니다. 추가 정보를 제공 하려면 다음 함수를 사용 합니다.  
  
 `__analysis_assume(`  `expr`  `)`  
  
 `expr`-true로 평가 된다고 간주 되는 모든 식입니다.  
  
 코드 분석 도구는 식이 나타내는 조건 함수 나타나고 식이 변경 될, 예를 들어 변수에 할당 될 때까지 true로 남아 있는 지점에서 true 있다고 가정 합니다.  
  
> [!NOTE]
>  `__analysis_assume`코드 최적화를 영향을 주지 않습니다. 코드 분석 도구를 사용 하는 외부 `__analysis_assume` no-op으로 정의 됩니다.  
  
## <a name="example"></a>예  
 다음 코드에서는 `__analysis_assume` 코드 분석 경고를 해결 하려면 [C6388](../code-quality/c6388.md):  
  
```  
#include<windows.h>  
#include<codeanalysis\sourceannotations.h>  
  
using namespace vc_attributes;  
  
// calls free and sets ch to null  
void FreeAndNull(char* ch);  
  
//requires pc to be null  
void f([Pre(Null=Yes)] char* pc);  
  
void test( )  
{  
  char *pc = (char*)malloc(5);  
  FreeAndNull(pc);  
  __analysis_assume(pc == NULL);   
  f(pc);  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [__assume](/cpp/intrinsics/assume)