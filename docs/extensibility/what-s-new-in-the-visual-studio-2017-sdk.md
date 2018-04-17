---
title: 어떤&#39;Visual Studio 2017 SDK의 새로운 s | Microsoft Docs
ms.custom: ''
ms.date: 10/31/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 9efcf0a3-dbde-4cab-8ed3-425826a48b2e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: abc1f12a5a6c7368bc47e8f4e924d109dcf87f57
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="what39s-new-in-the-visual-studio-2017-sdk"></a>어떤&#39;의 새로운 Visual Studio 2017 SDK

Visual Studio SDK는 Visual Studio 2017에 대 한 다음과 같은 새로운 기능과 업데이트 된 기능에 있습니다.

## <a name="vsix-v3-format"></a>VSIX v3 형식

Visual Studio 2017 새 경량 설치를 지원 하기 위해 VSIX 확장 매니페스트 형식 버전 3 (VSIX v3)으로 업데이트 되었습니다.

새 형식에 대 한 지원에 있습니다.

* 필수 구성 요소를 검색 하 고는 VSIXInstaller 하 여 설치를 명시적으로 선언 합니다.
* Ngen'ing 어셈블리에 확장을 설치 합니다.
* 일반적인 확장 루트를 벗어났습니다 자산을 설치 합니다.

이러한 변경 내용에 대해 알아보려면 다음 항목을 참조 합니다.

* [2017에 대 한 확장성에 대 한 변경](breaking-changes-2017.md)
* [VSIX v3의 Ngen 지원](ngen-support.md)
* [확장 폴더 외부에 설치](set-install-root.md)
* [Visual Studio 2017 확장성에 관한 질문과 대답](faq-2017.md)

## <a name="migrating-extensibility-project-to-visual-studio-2017"></a>Visual Studio 2017을 확장성 프로젝트 마이그레이션

Visual Studio 2017을 확장성 프로젝트 및 VSIX 매니페스트를 업데이트 하는 방법을 알아보려면 참조 [하는 방법: Visual Studio 2017을 확장성 프로젝트 마이그레이션](how-to-migrate-extensibility-projects-to-visual-studio-2017.md)합니다.

## <a name="custom-project-and-item-templates"></a>사용자 지정 프로젝트 및 항목 템플릿

Visual Studio 2017 년부터 사용자 지정 프로젝트 및 항목 템플릿 검색 더 이상 수행 됩니다. 대신, 확장 이러한 서식 파일의 설치 위치를 설명 하는 템플릿 매니페스트 파일을 제공 해야 합니다. VSIX 확장을 업데이트 하려면 Visual Studio 2017을 사용할 수 있습니다. MSI를 사용 하 여 확장 프로그램을 배포 하는 경우 템플릿 매니페스트 파일을 직접 생성 해야 합니다. 자세한 내용은 참조 [사용자 지정 프로젝트 업그레이드 및 Visual Studio 2017에 대 한 항목 템플릿](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-2017.md)합니다. 템플릿 매니페스트 스키마에 설명 되어 [Visual Studio 템플릿 매니페스트 스키마 참조](../extensibility/visual-studio-template-manifest-schema-reference.md)합니다.

## <a name="updated-extension-performance-guidelines"></a>업데이트 된 확장 성능 지침

새로운 [하는 방법: 확장 성능 진단](how-to-diagnose-extension-performance.md) 아래 항목 [관리 Vspackage](managing-vspackages.md) 시작과 솔루션 로드 시간이 감지 하 여 Visual Studio에 확장 미치는 영향을 분석 하는 방법을 보여 주는 합니다.
