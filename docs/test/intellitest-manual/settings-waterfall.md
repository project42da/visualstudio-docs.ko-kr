---
title: "폭포수형 설정 | Microsoft IntelliTest 개발자 테스트 도구 | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliTest, Settings waterfall
ms.assetid: 45777037-9E16-4ABF-BD26-5AF4E740D4E6
caps.latest.revision: 56
ms.author: douge
manager: douge
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 45d36934cf1c46902cac566203cddf4a118b7fe4
ms.openlocfilehash: cb54407016434587396502ec22b019512813d084
ms.contentlocale: ko-kr
ms.lasthandoff: 06/02/2017

---
# <a name="settings-waterfall"></a>폭포수형 설정

폭포수형 설정의 개념은 사용자가 **어셈블리**, **설비** 및 **탐색** 수준에서 설정을 지정할 수 있음을 의미합니다. 

* 어셈블리 - [PexAssemblySettings](attribute-glossary.md#pexassemblysettings)
* 설비 - [PexClass](attribute-glossary.md#pexclass)
* 탐색 - [PexExplorationAttributeBase](attribute-glossary.md#pexexplorationattributebase)

**어셈블리** 수준에서 지정된 설정은 해당 어셈블리 아래 모든 설비 및 탐색에 영향을 줍니다. **설비** 수준에서 지정된 설정은 해당 설비 아래 모든 탐색에 영향을 줍니다. 자식 설정 우선: 설정이 **어셈블리** 및 **설비** 수준에서 지정된 경우 **설비** 설정이 사용됩니다.

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

아이디어와 기능 요청을 **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**에 게시하세요.

