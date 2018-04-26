---
title: 프로젝트 및 솔루션 파일 형식
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- File Properties.CopyToOutputDirectory
- File Properties.CustomToolNamespace
- File Properties.FileName
- File Properties.FullPath
- File Properties.BuildAction
- File Properties.CustomTool
- FileProperties
helpviewer_keywords:
- .sln files
- .suo files
- file types [Visual Studio]
- file extensions [Visual Studio]
- solution files [Visual Studio]
- sln files
- suo files
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b3786d6f38e4f87aa05a51b0a6112613bda65e56
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="project-and-solution-file-types"></a>프로젝트 및 솔루션 파일 형식

Visual Studio는 다양한 파일 형식을 지원합니다. 특정 설치에서는 설치된 구성 요소에 따라 지원되는 파일 형식이 결정됩니다. 이 항목에서는 일반적인 설치에서 지원되는 솔루션 및 프로젝트 파일 형식을 소개합니다.

## <a name="solution-files-sln-and-suo"></a>솔루션 파일(.sln 및 .suo)

Visual Studio에서는 .sln 및 .suo의 두 가지 파일 형식을 사용하여 솔루션 관련 설정을 저장합니다. 솔루션 파일로 총칭되는 이러한 파일은 솔루션 탐색기가 파일을 관리하기 위한 그래픽 인터페이스를 표시하는 데 필요한 정보를 제공합니다.

|확장명|이름|설명|
|---------------|----------|-----------------|
|.sln|Visual Studio 솔루션|프로젝트, 프로젝트 항목 및 솔루션 항목을 솔루션으로 구성합니다.|
|.suo|솔루션 사용자 옵션|중단점 등 Visual Studio에서 수행한 사용자 수준 사용자 지정을 추적합니다.|

## <a name="project-files"></a>프로젝트 파일

프로젝트에는 다양한 파일 형식이 포함될 수 있습니다. 예를 들어, C# 코드 파일은 확장명이 **.cs**이며d C++ 파일은 확장명이 **.cpp**입니다. 리소스는 **.resx** 파일에 저장되고 XAML은 **.xaml** 파일에 저장됩니다. [App.config](../../ide/managing-application-settings-dotnet.md) 파일에는 응용 프로그램 코드에 포함하지 말아야 하는 응용 프로그램 정보(&mdash;예: 연결 문자열)가 포함됩니다.

C++ 프로젝트에서 파일 형식에 대한 자세한 내용은 [Visual C++ 프로젝트용으로 만들어지는 파일 형식](/cpp/ide/file-types-created-for-visual-cpp-projects)을 참조하십시오.

## <a name="see-also"></a>참고 항목

- [솔루션 및 프로젝트](../../ide/solutions-and-projects-in-visual-studio.md)