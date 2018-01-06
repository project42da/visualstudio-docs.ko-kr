---
title: "방법: VSIX 패키지에 종속성을 추가 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- package reference
- package assembly
- package dll
- vsix reference
ms.assetid: 8f20177b-dab9-43a3-b959-81a591b451d6
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 27fbf8c079ca1270074d7cae683ef6f8127e2a5a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-dependency-to-a-vsix-package"></a>방법: VSIX 패키지에 종속성을 추가 합니다.

이미 대상 컴퓨터에 존재 하지 않는 모든 종속성을 설치 하는 VSIX 패키지 배포를 설정할 수 있습니다. 이를 위해 VSIX 종속성 source.extension.vsixmanifest 파일을 포함 합니다.

## <a name="to-add-a-dependency"></a>종속성 추가 하려면

1. source.extension.vsixmanifest 파일을 열고는 **디자인** 보기. 이동 하 여 **종속성** 탭을 클릭 **새로**합니다.

2. 설치 된 확장을 추가 하려면:에서 **새 종속성 추가** 대화 상자에서 **설치 된 확장** 선택한 후는 **이름**를 목록에서 확장을 선택 합니다.

3. 설치 되어 있지 않은 다른 VSIX를 추가 하려면::에서 **새 종속성 추가** 대화 상자에서 **파일 시스템에 파일이** 다음 사용 하 여는 **찾아보기** VSIX를 선택 하려면 단추입니다.

## <a name="require-a-specific-visual-studio-release"></a>특정 Visual Studio 릴리스에 필요

확장 프로그램이 특정 버전의 Visual Studio 2017이 필요한 경우 예를 들어 15.3에 릴리스된 기능에 따라, 프로그램 VSIX에 빌드 번호를 지정할 수 있습니다 **InstallationTarget**합니다. 예를 들어, 릴리스 15.3 '15.0.26730.3'의 빌드 번호를 있습니다. 릴리스 빌드 번호를 매핑 나타나면 [여기](../install/visual-studio-build-numbers-and-release-dates.md)합니다. 이때 릴리스를 사용 하 여 번호 '15.3' 제대로 작동 하지 것입니다.

확장 해야 15.3 하거나 선언 합니다 이상 경우는 **InstallationTarget 버전** 으로 [15.0.26730.3, 16.0):

```xml
<Installation>
  <InstallationTarget Id="Microsoft.VisualStudio.Community" Version="[15.0.26730.3, 16.0)" />
</Installation>
```

VSIXInstaller에서는 이전 버전의 Visual Studio를 검색 하 고 이후의 업데이트는 필요한 사용자에 게 알립니다.


## <a name="see-also"></a>참고 항목

 [VSIX 확장 스키마 1.0 참조](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b) [VSIX 패키지 분석](../extensibility/anatomy-of-a-vsix-package.md) [Windows Installer 배포에 대 한 확장을 준비 하는 중](../extensibility/preparing-extensions-for-windows-installer-deployment.md)