---
title: "Visual Studio 2017 SDK의 새로운 기능 | Microsoft 문서"
ms.custom: 
ms.date: 11/09/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9efcf0a3-dbde-4cab-8ed3-425826a48b2e
caps.latest.revision: 1
author: gregvanl
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: 8163a0e1230712734936b7548bef1753ee0c1d2a
ms.openlocfilehash: 3da360fc4df5516f5d976f807319c07b49d8c4e8
ms.lasthandoff: 03/07/2017

---
# <a name="what39s-new-in-the-visual-studio-2017-sdk"></a>Visual Studio 2017 SDK의 새로운 기능

Visual Studio SDK는 Visual Studio 2017에 대 한 다음과 같은 새로운 기능과 업데이트 된 기능에 있습니다.

## <a name="vsix-v3-format"></a>VSIX v3 형식

Visual Studio 2017 새 간단한 설치를 지원 하려면 VSIX 확장 매니페스트 형식 버전 3 (VSIX v3)으로 업데이트 되었습니다.

새 형식에 대 한 지원을 있습니다.

* 필수 구성 요소를 감지 하 고는 VSIXInstaller 하 여 설치를 명시적으로 선언 합니다.
* Ngen'ing 어셈블리에 확장을 설치 합니다.
* 일반적인 확장 루트 외부 자산을 설치 합니다.

이러한 변경에 대해 알아보려면 다음 항목을 참조 합니다.

* [확장성 2017에 대 한 변경 내용](breaking-changes-2017.md)
* [VSIX v3의 Ngen 지원](ngen-support.md)
* [확장 폴더 외부에 설치](set-install-root.md)
* [Visual Studio 2017 확장성에 대 한 자주 묻는 질문](faq-2017.md)

## <a name="migrating-extensibility-project-to-visual-studio-2017"></a>Visual Studio 2017를 마이그레이션 확장성 프로젝트

Visual Studio 2017를 확장성 프로젝트 및 해당 VSIX 매니페스트를 업데이트 하는 방법을 알아보려면 다음을 참조 [하는 방법: Visual Studio 2017를 확장성 프로젝트 마이그레이션](how-to-migrate-extensibility-projects-to-visual-studio-2017.md)합니다.

## <a name="lightweight-solution-load-lsl"></a>간단한 솔루션 로드 (LSL)

간단한 솔루션 로드는 보다 신속 하 게 생산성을 높일 수 있도록 솔루션 로드 시간을 크게 줄일 수 있는 VS 2017의 새로운 기능입니다. LSL 사용 하는 경우 Visual Studio 로드 되지 않습니다 완벽 하 게 프로젝트와 작업을 시작 하기 전까지.

LSL Visual Studio 확장 프로그램을 변화 시킬 수 있습니다. 확장 된 기능은 완전히 로드 되 고 프로젝트에 따라 다릅니다 수 작동 없거나 제대로 작동 합니다. 참조 [Lightweight 솔루션 로드](lightweight-solution-load-extension-impact.md) 확장 영향을 받을 수와 확장 업데이트에 대 한 지침을 확인 여부를 익힐 수 있습니다.

## <a name="custom-project-and-item-templates"></a>사용자 지정 프로젝트 및 항목 템플릿

Visual Studio 2017 년부터 사용자 지정 프로젝트 및 항목 템플릿 검색은 더 이상 수행 됩니다. 대신, 확장 이러한 서식 파일의 설치 위치를 설명 하는 템플릿 매니페스트 파일을 제공 해야 합니다. Visual Studio 2017 VSIX 확장 업데이트를 사용할 수 있습니다. MSI를 사용 하 여 확장 프로그램을 배포 하는 경우 템플릿 매니페스트 파일을 수동으로 생성 해야 합니다. 자세한 내용은 참조 [사용자 지정 프로젝트 업그레이드 및 Visual Studio 2017에 대 한 항목 템플릿](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-2017.md)합니다. 템플릿 매니페스트 스키마에 설명 되어 [Visual Studio 템플릿 매니페스트 스키마 참조](../extensibility/visual-studio-template-manifest-schema-reference.md)합니다.

## <a name="updated-extension-performance-guidelines"></a>업데이트 된 확장 성능 지침

새로운 [하는 방법: 확장 성능 진단](how-to-diagnose-extension-performance.md) 항목 [관리 Vspackage](managing-vspackages.md) 시작 하 고 솔루션 로드 시간을 감지 하 여 Visual Studio에 확장 영향 분석 하는 방법을 보여 줍니다.

