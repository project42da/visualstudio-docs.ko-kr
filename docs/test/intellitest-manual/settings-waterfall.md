---
title: 폭포수형 설정 | Microsoft IntelliTest 개발자 테스트 도구
ms.date: 05/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Settings waterfall
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 1abe2192ab919d1519c0a95f4b58bdfe1d82aacb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="settings-waterfall"></a>폭포수형 설정

폭포수형 설정의 개념은 사용자가 **어셈블리**, **설비** 및 **탐색** 수준에서 설정을 지정할 수 있음을 의미합니다.

* 어셈블리 - [PexAssemblySettings](attribute-glossary.md#pexassemblysettings)
* 설비 - [PexClass](attribute-glossary.md#pexclass)
* 탐색 - [PexExplorationAttributeBase](attribute-glossary.md#pexexplorationattributebase)

**어셈블리** 수준에서 지정된 설정은 해당 어셈블리 아래 모든 설비 및 탐색에 영향을 줍니다. **설비** 수준에서 지정된 설정은 해당 설비 아래 모든 탐색에 영향을 줍니다. 자식 설정 우선&mdash;설정이 **어셈블리** 및 **설비** 수준에서 지정된 경우 **설비** 설정이 사용됩니다.

일부 설정은 **어셈블리** 수준 또는 **설비** 수준에만 관련됩니다.

**예제**

```
using Microsoft.Pex.Framework;

[assembly: PexAssemblySettings(MaxBranches = 1000)] // we override the default value of maxbranches

namespace MyTests
{
    [PexClass(MaxBranches = 500)] // we override the 1000 value and set maxbranches to 500 
    public partial class MyTests
    {
        [PexMethod(MaxBranches = 100)] // we override again, maxbranches = 100
        public void MyTest(...) { ... }
    }
}
```

## <a name="got-feedback"></a>피드백이 있으신가요?

아이디어와 기능 요청을 [UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)에 게시하세요.
