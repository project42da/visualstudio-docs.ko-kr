---
title: "Visual Studio에서 템플릿을 검색 문제 해결 | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 72663d56844fcc34164e9408ab14c8ead234683e
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="troubleshooting-template-installation"></a>템플릿을 설치 문제 해결

프로젝트 또는 항목 템플릿 배포 문제를 실행 하는 경우 진단 로깅을 사용할 수 있습니다.

1. 다음과 같은 내용으로 Common7\IDE\CommonExtensions 폴더에 설치 (예: C:\Program Files (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CommonExtensions\EnablePkgDefLogging.pkgdef)에 대 한 pkgdef 파일을 만듭니다.

    ```
    [$RootKey$\VsTemplate]
    "EnableTemplateDiscoveryLog"=dword:00000001
    ```

1. 설치를 위한 Windows 검색에서 검색 하 여 "개발자 명령 프롬프트"를 열고 실행 `devenv /updateConfiguration`합니다.

1. Visual Studio를 시작 하 고 두 템플릿 트리를 초기화 하 여 새 프로젝트와 새 항목 대화 상자를 시작 합니다. 서식 파일 로그에 나타납니다 **%LOCALAPPDATA%\Microsoft\VisualStudio\15.0_[instanceid]\VsTemplateDiagnosticsList.csv** (instanceid는 Visual Studio 인스턴스를 설치 ID에 해당). 각 서식 파일 트리 초기화가이 로그에 항목을 추가 합니다.

로그 파일에는 다음과 같은 열을 포함 되어 있습니다.

- **FullPathToTemplate**에 다음 값입니다.

    - 매니페스트 기반 배포에 대 한 1

    - 디스크 기반 배포에 대 한 0

- **TemplateFileName**

- 다른 템플릿 속성

> [!NOTE]
> 로깅을 사용 하지 않으려면, pkgdef 파일을 제거 하거나 변경의 값 `EnableTemplateDiscoveryLog` 를 `dword:00000000`, 한 다음 실행 `devenv /updateConfiguration` 다시 합니다.

## <a name="see-also"></a>참고 항목

[사용자 지정 프로젝트 및 항목 템플릿 만들기](creating-custom-project-and-item-templates.md)