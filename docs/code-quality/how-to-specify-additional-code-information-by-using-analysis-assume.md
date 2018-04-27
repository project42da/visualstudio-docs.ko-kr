---
title: '방법: _Analysis_assume를 사용 하 여 추가 코드 정보를 지정 합니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- _Analysis_assume
helpviewer_keywords:
- _Analysis_assume
ms.assetid: 51205d97-4084-4cf4-a5ed-3eeaf67deb1b
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: ce8102bbc790019490c4dc2a2ccbfab7d8c33981
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-specify-additional-code-information-by-using-analysisassume"></a>방법: _Analysis_assume를 사용 하 여 추가 코드 정보를 지정 합니다.
C/c + + 코드를 분석 프로세스는 데 도움이 되 고 줄어들지만 경고에 대 한 코드 분석 도구에 대 한 힌트를 제공할 수 있습니다. 추가 정보를 제공 하려면 다음 함수를 사용 합니다.

 `_Analysis_assume(`  `expr`  `)`

 `expr` -true로 평가 된다고 간주 되는 모든 식입니다.

 코드 분석 도구는 식이 나타내는 조건 함수 나타나고 식이 변경 될, 예를 들어 변수에 할당 될 때까지 true로 남아 있는 지점에서 true 있다고 가정 합니다.

> [!NOTE]
>  `_Analysis_assume` 코드 최적화를 영향을 주지 않습니다. 코드 분석 도구를 사용 하는 외부 `_Analysis_assume` no-op으로 정의 됩니다.

## <a name="example"></a>예제
 다음 코드에서는 `_Analysis_assume` 코드 분석 경고를 해결 하려면 [C6388](../code-quality/c6388.md):

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
  _Analysis_assume(pc == NULL);
  f(pc);
}
```

## <a name="see-also"></a>참고 항목
 [__assume](/cpp/intrinsics/assume)