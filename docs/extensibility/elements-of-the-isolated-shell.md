---
redirect_url: shell/elements-of-the-isolated-shell
title: "격리 셸 요소의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode
ms.assetid: f8d68c3d-9134-4a8f-b566-485956cd321e
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 15c32ccd3634529c63eb95eb698c3239b6c0e37e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="elements-of-the-isolated-shell"></a>격리 셸의 요소
레지스트리 설정, 실행 시간 설정 및 응용 프로그램 진입점 격리 셸 응용 프로그램 및.vsct,.pkgdef, and.pkgundef 파일을 수정할 수 있습니다.  
  
## <a name="registry-settings"></a>레지스트리 설정  
 .pkgdef와.pkgundef 파일 격리 셸 응용 프로그램에 대 한 레지스트리 설정을 수정합니다. 응용 프로그램을 실행 하는 경우 다음과 같은 순서로 레지스트리 설정이 정의 됩니다.  
  
 응용 프로그램을 실행 하는 경우 다음과 같은 순서로 레지스트리 설정이 정의 됩니다.  
  
1.  응용 프로그램에 대 한 레지스트리 키가 만들어집니다.  
  
2.  레지스트리에 지정 된 키와 항목을 정의 하 여 응용 프로그램의.pkgdef 파일에서 업데이트 됩니다.  
  
3.  응용 프로그램의 일부인 모든 패키지에 대 한 레지스트리는 해당 패키지의.pkgdef 파일에서 업데이트 됩니다. 각 패키지 $RootKey$ \Packages 하 여 응용 프로그램의.pkgdef 파일에 정의 된\\{*vsPackageGuid*} 패키지에 대 한 키입니다.  
  
4.  레지스트리 AppEnvConfig.pkgdef 및에서 BaseConfig.pkgdef에서 업데이트 되는 *Visual Studio SDK 설치 경로*\Common7\IDE\ShellExtensions\Platform 디렉터리입니다. 이러한 파일은 Visual Studio의 일부 및 또한 Visual Studio Shell (격리 모드) 재배포 가능 패키지의 일부입니다.  
  
5.  레지스트리에 지정 된 키와 항목을 제거 하 여 응용 프로그램의.pkgundef 파일에서 업데이트 됩니다.  
  
## <a name="run-time-settings"></a>런타임 설정  
 사용자 격리 셸 응용 프로그램을 시작할 때 Visual Studio shell의 시작 진입점을 호출 합니다. 응용 프로그램 설정은 응용 프로그램이 시작 되 면 다음과 같이 정의 됩니다.  
  
1.  Visual Studio shell 특정 키에 대 한 응용 프로그램 레지스트리를 확인합니다. 시작 진입점에 대 한 호출에는 키에 대 한 설정을 지정 하는 경우 해당 값의 레지스트리 값을 재정의 합니다.  
  
2.  레지스트리 나 항목 지점이 있는 경우 설정의 값을 지정 하는 매개 변수 다음 설정에 대해 기본값이 사용 됩니다.  
  
 명령줄에서 응용 프로그램을 시작 하면 모든 명령줄 스위치와 동일한 방식으로 Devenv에이 처리 하는 Visual Studio shell에 전달 됩니다. Devenv 스위치에 대 한 자세한 내용은 참조 [Devenv 명령줄 스위치](../ide/reference/devenv-command-line-switches.md) 및 [VSPackage 개발에 대 한 Devenv 명령줄 스위치](../extensibility/devenv-command-line-switches-for-vspackage-development.md)합니다. 명령줄 스위치에 대 한 패키지를 등록 하는 방법에 대 한 자세한 내용은 참조 [추가 명령줄 스위치](../extensibility/adding-command-line-switches.md)합니다.  
  
## <a name="the-start-entry-point"></a>시작 진입점  
 Appenvstub.dll 파일 격리 셸에 액세스 하기 위한 진입점을 포함 합니다. 응용 프로그램이 시작 될 때 시작 항목 Appenvstub.dll 포인트를 호출 합니다.  
  
 시작 진입점에 전달 되는 마지막 매개 변수 값을 변경 하 여 응용 프로그램의 동작을 변경할 수 있습니다. 자세한 내용은 참조 [격리 셸 항목 지점 매개 변수 (c + +)](../extensibility/isolated-shell-entry-point-parameters-cpp.md)합니다.  
  
## <a name="the-vsct-file"></a>합니다. Vsct 파일  
 .Vsct 파일에는 응용 프로그램에서 사용할 수 있는 표준 Visual Studio UI 요소를 지정할 수 있습니다. 자세한 내용은 참조 [합니다. Vsct 파일](../extensibility/modifying-the-isolated-shell-by-using-the-dot-vsct-file.md)합니다.  
  
## <a name="the-pkgundef-file"></a>합니다. Pkgundef 파일  
 응용 프로그램이 Visual Studio가 이미 설치 된 컴퓨터에 설치 되 면 응용 프로그램에 대 한 Visual Studio 레지스트리 항목의 복사본이 이루어집니다. 기본적으로 응용 프로그램이 컴퓨터에 이미 설치 되어 있는 Vspackage를 사용 합니다. .Pkgundef 파일에는 응용 프로그램에서 Visual Studio 셸 또는 확장의 특정 요소를 제거 하려면 레지스트리 항목을 제외할 수 있습니다. 자세한 내용은 참조 [합니다. Pkgundef 파일](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgundef-file.md)합니다.  
  
 .Pkgundef 파일에는 응용 프로그램에서 Visual Studio 셸 또는 확장의 특정 요소를 제거 하려면 레지스트리 항목을 제외할 수 있습니다. 자세한 내용은 참조 [합니다. Pkgundef 파일](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgundef-file.md)합니다.  
  
 패키지를 제외할 수 있습니다 하는 Guid의 집합에 나열 된 [Visual Studio 기능의 패키지 Guid](../extensibility/package-guids-of-visual-studio-features.md)합니다.  
  
## <a name="the-pkgdef-file"></a>합니다. Pkgdef 파일  
 .Pkgdef 파일에는 응용 프로그램을 설치할 때 설정 된 응용 프로그램에 대 한 레지스트리 항목을 정의할 수 있습니다. .Pkgdef 파일에 대 한 설명 및 Visual Studio 셸에서 사용 하는 레지스트리 항목의 목록에 대 한 참조 [합니다. Pkgdef 파일](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)합니다.  
  
## <a name="substitution-strings"></a>대체 문자열  
 .Pkgdef 및.pkgundef 파일에 사용 되는 대체 문자열에 나열 된 [대체 문자열이에 사용 합니다. Pkgdef 및 합니다. Pkgundef 파일](../extensibility/substitution-strings-used-in-dot-pkgdef-and-dot-pkgundef-files.md)합니다.  
  
## <a name="other-settings"></a>기타 설정  
 격리 셸 응용 프로그램 Microsoft.VisualStudio.GraphModel.dll에 의존 하는 경우 격리 셸 응용 프로그램의.config 파일에 다음 바인딩 리디렉션을 추가 해야 합니다.  
  
```  
<dependentAssembly>  
    <assemblyIdentity name="Microsoft.VisualStudio.GraphModel" publicKeyToken="b03f5f7f11d50a3a" culture="neutral" />  
    <bindingRedirect oldVersion="11.0.0.0" newVersion="12.0.0.0"/>  
</dependentAssembly>  
  
```