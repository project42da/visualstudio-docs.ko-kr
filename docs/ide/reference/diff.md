---
title: -Diff
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
ms.assetid: 5377fedb-632a-4e86-a947-7c11c86451e7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 81c70c238a4503fbd05249ef6522cf020c00221c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="diff"></a>/Diff
두 파일을 비교합니다. 차이점은 특별한 Visual Studio 창에 표시됩니다.

## <a name="syntax"></a>구문

```
devenv /Diff SourceFile, TargetFile, [SourceDisplayName],[TargetDisplayName]
```

## <a name="arguments"></a>인수
 `SourceFile`

 필수. 비교할 첫 번째 파일의 전체 경로와 이름입니다.

 `TargetFile`

 필수. 비교할 두 번째 파일의 전체 경로와 이름입니다.

 `SourceDisplayName`

 선택 사항입니다. 첫 번째 파일의 표시 이름입니다.

 `TargetDisplayName`

 선택 사항입니다. 두 번째 파일의 표시 이름입니다.