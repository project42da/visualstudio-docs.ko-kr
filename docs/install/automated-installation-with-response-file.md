---
title: "지시 파일을 사용하여 Visual Studio 설치 자동화 | Microsoft Docs"
description: '{{PLACEHOLDER}}'
ms.date: 05/06/2017
ms.reviewer: tims
ms.suite: 
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 448C738E-121F-4B64-8CA8-3BC997817A14
author: timsneath
ms.author: tims
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 85576806818a6ed289c2f660f87b5c419016c600
ms.openlocfilehash: 2c709b5aa90ff4f5f70f0411c7f4f1870d1725d4
ms.contentlocale: ko-kr
ms.lasthandoff: 05/09/2017

---
# <a name="how-to-define-settings-in-a-response-file"></a>지시 파일에서 설정을 정의하는 방법
Visual Studio를 배포하는 관리자는 `--in` 매개 변수를 사용하여 지시 파일을 지정할 수 있습니다. 예를 들면 다음과 같습니다.

```
vs_enterprise.exe --in customInstall.json
```

지시 파일은 명령줄 인수를 미러링하는 콘텐츠가 포함된 [JSON](http://json-schema.org/) 파일입니다.  일반적으로 명령줄 매개 변수가 인수(예: `--quiet`, `--passive` 등)를 사용하지 않으면 지시 파일의 값은 true/false여야 합니다.  매개 변수가 인수(예: `--installPath <dir>`)를 사용하면 지시 파일의 값은 문자열이어야 합니다.  매개 변수가 인수를 사용하고 명령줄에 두 번 이상 나타날 수 있으면(예: `--add <id>`) 값은 문자열 배열이어야 합니다.

명령줄에 제공된 입력이 지시 파일의 설정과 병합되는 여러 입력을 사용하는 매개 변수의 경우를 제외하고(예: `--add`) 명령줄에 지정된 매개 변수는 지시 파일의 설정을 재정의합니다.

# <a name="setting-a-default-configuration-for-visual-studio"></a>Visual Studio에 대한 기본 구성 설정

`--layout`을 사용하여 네트워크 레이아웃 캐시를 만든 경우 초기 `response.json` 파일은 레이아웃에서 만들어집니다.

레이아웃을 만드는 관리자는 `response.json` 파일을 수정하여 사용자가 레이아웃에서 Visual Studio를 설치할 때 표시되는 기본 설정을 제어할 수 있습니다.  예를 들어 특정 워크로드 및 구성 요소를 기본적으로 설치하도록 선택하려는 관리자는 해당 항목을 추가하도록 `response.json` 파일을 구성할 수 있습니다.

Visual Studio 설치 프로그램이 레이아웃 폴더에서 실행되면 _자동으로_ 레이아웃 폴더의 지시 파일을 사용합니다.  `--in` 옵션을 사용할 필요가 없습니다.

오프라인 레이아웃 폴더에서 만들어진 `response.json` 파일을 업데이트하여 이 레이아웃에서 설치하는 사용자에 대한 기본 설정을 정의할 수 있습니다. **하지만 레이아웃이 만들어질 때 정의된 기존 속성을 그대로 유지해야 합니다.**

레이아웃의 기본 `response.json` 파일은 다음과 비슷하게 표시되지만 설치 중인 제품 및 채널에 대한 값이 포함됩니다.

```json
{
  "installChannelUri": ".\\ChannelManifest.json",
  "channelUri": "https://aka.ms/vs/15/release/channel",
  "installCatalogUri": ".\\Catalog.json",
  "channelId": "VisualStudio.15.Release",
  "productId": "Microsoft.VisualStudio.Product.Enterprise"
}
```

## <a name="example-layout-response-file-content"></a>레이아웃 지시 파일 콘텐츠의 예
이 예제에서는 영어 및 프랑스어 UI 언어를 사용하여 6개의 일반 워크로드 및 구성 요소가 포함된 Visual Studio Enterprise를 설치합니다. 이를 템플릿으로 사용할 수 있고, 이 경우 워크로드 및 구성 요소를 설치한 항목으로만 변경합니다.

```json
{
  "installChannelUri": ".\\ChannelManifest.json",
  "channelUri": "https://aka.ms/vs/15/release/channel",
  "installCatalogUri": ".\\Catalog.json",
  "channelId": "VisualStudio.15.Release",
  "productId": "Microsoft.VisualStudio.Product.Enterprise",

  "installPath": "C:\\VS2017",
  "quiet": false,
  "passive": false,
  "includeRecommended": true,
  "norestart": false,

  "addProductLang": [
    "en-US",
    "fr-FR"
    ],

    "add": [
        "Microsoft.VisualStudio.Workload.ManagedDesktop",
        "Microsoft.VisualStudio.Workload.Data",
        "Microsoft.VisualStudio.Workload.NativeDesktop",
        "Microsoft.VisualStudio.Workload.NetWeb",
        "Microsoft.VisualStudio.Workload.Office",
        "Microsoft.VisualStudio.Workload.Universal",
        "Component.GitHub.VisualStudio"
    ]
}
```

