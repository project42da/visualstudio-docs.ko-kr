---
title: 설정 가져오기 및 내보내기 명령
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- Tools.ImportandExportSettings
helpviewer_keywords:
- Tools.ImportandExportSettings
- Import and Export Settings command
ms.assetid: 94a06468-a44d-403d-a931-77bbc9d06e56
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a95841d9b9b8e67f34883efcc1a55a2daba7e8b7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="import-and-export-settings-command"></a>설정 가져오기 및 내보내기 명령
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 설정을 가져오거나, 내보내거나, 다시 설정합니다.

## <a name="syntax"></a>구문

```
Tools.ImportandExportSettings [/export:filename | /import:filename | /reset]
```

## <a name="switches"></a>스위치
 /export:`filename`

 선택 사항입니다. 현재 설정을 지정된 파일로 내보냅니다.

 /import:`filename`

 선택 사항입니다. 지정된 파일의 설정을 가져옵니다.

 /reset

 선택 사항입니다. 현재 설정을 다시 설정합니다.

## <a name="remarks"></a>설명

스위치 없이 이 명령을 실행하면 **설정 가져오기 및 내보내기** 마법사가 열립니다. 자세한 내용은 [설정 동기화](../../ide/synchronized-settings-in-visual-studio.md)를 참조하세요.

## <a name="example"></a>예

다음 명령은 현재 설정을 `MyFile.vssettings` 파일로 내보냅니다.

```shell
Tools.ImportandExportSettings /export:"c:\Files\MyFile.vssettings"
```

## <a name="see-also"></a>참고 항목

- [Visual Studio IDE 개인 설정](../../ide/personalizing-the-visual-studio-ide.md)
- [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)