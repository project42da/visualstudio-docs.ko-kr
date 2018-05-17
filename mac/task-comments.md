---
title: 작업 주석
description: 코드에 작업 주석 추가
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: 562DCB46-D8FA-4DC4-AAEA-F274448C4CD2
ms.openlocfilehash: ca74c6429ed721a6c11bd71d024668cc695274e9
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="task-comments"></a>작업 주석

코드를 작성할 때는 미완성 코드, 의심스러운 코드 또는 임시방편 코드에 주석을 달아 주의 사항을 기재하는 것이 일반적인 관행입니다. Mac용 Visual Studio에서 제공하는 기본 신호 토큰은 TODO, HACK, FIXME 및 UNDONE입니다. 다음 이미지와 같이 **Visual Studio > 기본 설정... > 환경 > 작업**에서 개인화된 토큰을 정의할 수 있습니다.

 ![작업 목록 기본 설정](media/source-editor-image10.png)

새 작업 주석을 추가하려면 작업 키워드가 포함된 주석을 추가합니다. 예:

```
//TODO: Finish this for all properties.
```

Mac용 Visual Studio는 작업 목록 패드에서 이러한 표식을 강조 표시하여 주의를 환기합니다. 작업 목록 패드를 표시하려면 **보기 > 패드 > 작업**로 이동합니다.

![작업 목록 패드](media/source-editor-image11.png)