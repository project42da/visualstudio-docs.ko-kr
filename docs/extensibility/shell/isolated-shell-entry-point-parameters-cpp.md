---
title: "격리 셸 진입점 매개 변수 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Shell [Visual Studio], isolated mode, Start entry point
- Visual Studio shell, isolated mode, Start entry point
ms.assetid: 18f4b18b-2173-4afa-ba0a-42fe33e61118
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 78993e12c1ab4098e20aad243faaa487ff0ea35b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isolated-shell-entry-point-parameters-c"></a>격리 셸 진입점 매개 변수 (c + +)
Visual Studio 셸 기반 응용 프로그램이 시작 되 면 Visual Studio shell의 시작 진입점을 호출 합니다. 셸의 시작 진입점에 대 한 호출에서 다음 설정은 재정의할 수 있습니다. 각 설정에 대 한 참조 [합니다. Pkgdef 파일](modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)합니다.  
  
-   AddinsAllowed  
  
-   AllowsDroppedFilesOnMainWindow  
  
-   응용 프로그램 이름  
  
-   CommandLineLogo  
  
-   DefaultHomePage  
  
-   DefaultProjectsLocation  
  
-   DefaultSearchPage  
  
-   DefaultUserFilesFolderRoot  
  
-   DisableOutputWindow  
  
-   HideMiscellaneousFilesByDefault  
  
-   HideSolutionConcept  
  
-   NewProjDlgInstalledTemplatesHdr  
  
-   NewProjDlgSlnTreeNodeTitle  
  
-   SolutionFileCreatorIdentifier  
  
-   SolutionFileExt  
  
-   UserFilesSubFolderName  
  
-   UserOptsFileExt  
  
 Visual Studio 셸 격리 서식 파일은 소스 파일을 만듭니다 *solutionName*.cpp, 여기서 *solutionName* 응용 프로그램에 대 한 솔루션 이름입니다. 이 파일 _tWinMain 함수가 응용 프로그램에 대 한 주 진입점을 정의합니다. 이 함수는 셸의 시작 진입점을 호출합니다.  
  
 응용 프로그램이 시작 될 때 이러한 설정을 변경 하 여 응용 프로그램의 동작을 변경할 수 있습니다.  
  
## <a name="parameters"></a>매개 변수  
 Visual Studio shell의 시작 진입점 5 개의 매개 변수를 정의합니다. 처음 네 개의 매개 변수를 변경 하지 마십시오. 다섯 번째 매개 변수 설정 재정의 목록을 사용 합니다. 셸의 시작 진입점 응용 프로그램의 주 진입점에서 호출 됩니다.  
  
 셸의 시작 진입점에는 다음 서명이 있습니다.  
  
```  
typedef int (__cdecl *STARTFCN)(LPSTR, LPWSTR, int, GUID *, WCHAR *pszSettings);  
```  
  
 응용 프로그램 설정 보다 우선, 설정의 값을 지정 하지 않을 경우 매개 변수는 null 포인터에 우선 합니다.  
  
 하나 이상의 설정을 재정의 하려면 재정의 해야 하는 설정을 포함 하는 유니코드 문자열을 전달 합니다. 문자열은 이름-값 쌍의 세미콜론으로 구분 된 목록. 각 쌍 뒤에 등호 (=)로 시작 하는 설정에 적용할 값을 재정의 하려면 설정의 이름을 포함 합니다.  
  
> [!NOTE]
>  유니코드 문자열에 공백을 포함 하지 마십시오.  
  
 다음 문자열을 부울 설정에 대 한 값이 true;를 나타내며합니다 다른 모든 문자열 false를 값을 나타냅니다. 이러한 문자열 대/소문자를 구분 하지 않습니다.  
  
-   \+  
  
-   1  
  
-   -1  
  
-   위치  
  
-   true  
  
-   예  
  
## <a name="example"></a>예  
 추가 기능을 사용 하지 않도록 설정 하 고 응용 프로그램에 대 한 기본 프로젝트 위치를 변경 하려면 "AddinsAllowed=false;DefaultProjectsLocation=%USERPROFILE%\temp"에 대 한 마지막 매개 변수를 설정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [격리 셸 사용자 지정](customizing-the-isolated-shell.md)   
 [. Pkgdef 파일](modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)