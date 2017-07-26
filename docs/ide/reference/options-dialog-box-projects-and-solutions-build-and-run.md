---
title: "옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행 | Microsoft Docs"
ms.custom: 
ms.date: 7/14/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Projects.Build_and_Run
- VS.ToolsOptionsPag.Projects.Build_and_Run
helpviewer_keywords:
- builds [Visual Studio], setting up
- run actions
- debugger, run options
ms.assetid: c884976e-c0df-4c6d-8e3a-856ea2bd547c
caps.latest.revision: 20
author: kempb
ms.author: kempb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: dc7a0c10390de67b56a83d2824224bed24125db0
ms.openlocfilehash: 974a032e57397592b7c09bffe28c55cb02c01a0a
ms.contentlocale: ko-kr
ms.lasthandoff: 07/17/2017

---

# <a name="options-dialog-box--projects-and-solutions-build-and-run"></a>옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행

이 대화 상자에서 동시에 빌드할 수 있는 Visual C++ 또는 Visual C# 프로젝트의 최대 개수, 특정 기본 빌드 동작 및 일부 빌드 로그 설정을 지정할 수 있습니다. 이러한 옵션에 액세스하려면 **도구 > 옵션**을 선택하고 **프로젝트 및 솔루션**을 확장한 후 **빌드 및 실행**을 선택합니다.
  
**최대 병렬 프로젝트 빌드 수**  
동시에 빌드할 수 있는 Visual C++ 및 Visual C# 프로젝트의 최대 개수를 지정합니다. 빌드 프로세스를 최적화하기 위해 최대 병렬 프로젝트 빌드 수는 자동으로 컴퓨터의 CPU 수로 설정됩니다. 최대값은 32입니다.  

**실행할 때 시작 프로젝트와 종속성만 빌드**  
F5 키를 사용하고 **디버그 > 시작** 메뉴 명령 또는 **빌드** 메뉴의 해당 명령을 선택할 때 시작 프로젝트와 종속성만 빌드합니다. 선택하지 않으면 모든 프로젝트와 종속성이 빌드됩니다. 

**실행 시 프로젝트가 만료된 경우**  
*[!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 프로젝트에만 적용됩니다.*

F5 키 또는 **디버그 > 시작** 명령으로 프로젝트 실행 시 기본 설정인 **빌드 여부 묻기**에서 프로젝트 구성이 만료되었는지를 묻는 메시지를 표시합니다. 실행될 때마다 프로젝트를 빌드하려면 **항상 빌드**를 선택합니다. 프로젝트를 실행할 때 모든 자동 빌드를 표시하지 않으려면 **빌드 안 함**을 선택합니다.

**실행 시 빌드 또는 배포 오류가 발생한 경우**  
*[!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 프로젝트에만 적용됩니다.*

F5 키 또는 **디버그 > 시작** 명령으로 프로젝트 실행 시 기본 설정인 **시작 여부 묻기**에서 빌드에 실패한 경우에도 프로젝트를 실행할지를 묻는 메시지를 표시합니다. 마지막으로 성공한 빌드를 자동으로 시작하려면 **이전 버전 시작** 을 선택합니다. 그러면 실행 중인 코드와 소스 코드 간에 불일치가 발생할 수 있습니다. 메시지를 표시하지 않으려면 **시작하지 않음**을 선택합니다.

**새 솔루션에 대해 현재 선택한 프로젝트를 시작 프로젝트로 사용**  
이 옵션을 설정하면 새 솔루션에서 현재 선택한 프로젝트를 시작 프로젝트로 사용합니다.  

**MSBuild 프로젝트 빌드 출력의 자세한 정도**  
빌드에 대한 **출력** 창에 표시되는 정보의 양을 결정합니다.  

**MSBuild 프로젝트 빌드 로그 파일의 자세한 정도**  
*[!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 프로젝트에만 적용됩니다.*

\\...\\*ProjectName*\Debug\\*ProjectName*.log에 있는 빌드 로그 파일에 작성되는 정보의 양을 결정합니다.  

## <a name="see-also"></a>참고 항목  
-[컴파일 및 빌드](../../ide/compiling-and-building-in-visual-studio.md)
- [옵션 대화 상자, 프로젝트 및 솔루션](../../ide/projects-and-solutions-options-dialog-box.md)
- [옵션 대화 상자, 프로젝트 및 솔루션, 웹 프로젝트](../../ide/reference/options-dialog-box-projects-and-solutions-web-projects.md)
