---
title: "사용자 지정 시작 페이지 배포 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- package start page
- deploy start page
ms.assetid: 4a7eb360-de83-41d5-be53-3cfb160d19f9
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c52a71ebb521f84f96bead09502389f6b395e90c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-custom-start-pages"></a>사용자 지정 시작 페이지를 배포합니다.
VSIX 배포를 사용 하 여 또는 대상 컴퓨터의 올바른 위치에 파일을 복사 하 여 사용자 지정 시작 페이지를 배포할 수 있습니다.  
  
## <a name="vsix-deployment-by-using-the-start-page-project-template"></a>시작 페이지 프로젝트 템플릿을 사용 하 여 VSIX 배포  
 시작 페이지 프로젝트 템플릿을 사용 하 여 시작 페이지를 만들 후 프로젝트를 빌드할 때 Visual Studio를 배포할 수는.vsix 파일을 만듭니다. .Vsix 파일에 시작 페이지를 패키징 배포의 경우 사용자에 따라 다음 옵션을 제공 합니다.  
  
-   네트워크 공유 나 공용 웹 사이트에.vsix 파일을 넣을 수 있습니다. 파일을 열 때 시작 페이지는 자동으로 설치 됩니다.  
  
-   .Vsix 파일을 업로드할 수는 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847) 웹 사이트 사용자가 사용 하 여 설치할 수 있도록 **확장 관리자**합니다.  
  
 시작 페이지 프로젝트 템플릿은 복사본을 수정 하 고 원래 유지할 수 있도록 기본 Visual Studio 시작 페이지의 복사본을 만듭니다.  
  
 시작 페이지 프로젝트 템플릿을 사용 하 여 얻을 수 있습니다 **확장 관리자** 하거나 웹 사이트에서 다운로드 합니다.  
  
## <a name="vsix-deployment-without-using-the-start-page-project-template"></a>시작 페이지 프로젝트 템플릿을 사용 하지 않고 VSIX 배포  
 VSIX 배포를 성공적으로 인식 되는 VSIX 등록 프로세스 및 폴더에 설치 되도록 확장이 필요 **확장 관리자**합니다. 시작 페이지 프로젝트 템플릿을 이미 올바른 폴더를 지정 하기 때문에는 VSIX 배포에 대 한 확장을 패키지할 때마다 사용 하는 것이 좋습니다. 그러나 서식 파일을 사용할 수 없습니다는 대/소문자를 사용 하도록 설정한 경우 사용 하지 않고 VSIX 배포를 만들 수 있습니다.  
  
 시작 페이지 프로젝트 템플릿을 사용 하지 않고 VSIX 배포를 만들려면 먼저 이러한 두 가지 방법 중 하나로 시작 페이지에 대 한.vsix 파일을 만듭니다.  
  
-   빈 VSIX 프로젝트에 사용자 지정 시작 페이지 파일을 추가 하 여 합니다. 자세한 내용은 참조 [VSIX 프로젝트 템플릿은](../extensibility/vsix-project-template.md)합니다.  
  
-   .Vsix 파일을 수동으로 만듭니다. .Vsix 파일을 수동으로 만들려면:  
    
    1.  새 폴더에 extension.vsixmanifest 파일 및 [Content_Types].xml 파일을 만듭니다. 자세한 내용은 참조 [VSIX 패키지 분석](/visualstudio/extensibility/anatomy-of-a-vsix-package)합니다.  
  
    2.  Windows 탐색기에서 두 개의 XML 파일이 포함 된 폴더를 마우스 오른쪽 단추로 클릭 보내기를 클릭 한 다음 압축 (zip) 폴더를 클릭 합니다. 결과.zip 파일을 Filename은 패키지를 설치 하는 재배포 가능 파일의 이름 Filename.vsix을 바꿉니다.  
  
 Visual studio 시작 페이지를 인식할는 `Content Element` VSIX 매니페스트의 포함 해야 합니다는 `CustomExtension Element` 올려진는 `Type` 특성이로 설정 `"StartPage"`합니다. VSIX 배포를 사용 하 여 설치 된 시작 페이지 확장에 표시 된 **시작 페이지 사용자 지정** 목록에 **시작** 옵션으로 페이지 **[설치 된 확장]** *확장 이름*합니다.  
  
 시작 페이지 패키지 어셈블리를 포함 하는 경우 Visual Studio가 시작 될 때 사용할 수 있도록 바인딩 경로 등록을 추가 해야 합니다. 이렇게 하려면 패키지에 다음 정보가 포함 된.pkgdef 파일이 포함 되어 있는지 확인 합니다.  
  
```  
[$RootKey$\BindingPaths\{Insert a new GUID here}]  
"$PackageFolder$"=""  
```  
  
### <a name="vsix-deployment-for-all-users"></a>모든 사용자에 대해 VSIX 배포  
 기본적으로 VSIX 패키지에서 배포 된 확장은 현재 사용자에 대해서만 설치 합니다. 모든 사용자가 배포를 만들어 대상 컴퓨터의 모든 사용자에 대 한 설치를 시작 페이지를 만들 수 있습니다.  
  
##### <a name="to-create-an-all-users-deployment"></a>모든 사용자가 배포를 만들려면  
  
1.  코드 뷰에서 extension.vsixmanifest 파일을 엽니다.  
  
2.  에 `Identifier` 추가 vsix 매니페스트의 요소는 `AllUsers` 의 값을 가진 요소가 `true`합니다.  
  
    ```  
    <AllUsers>true</AllUsers>  
    ```  
  
     그러면 vsix 설치를 묻는 메시지를 관리자 권한으로 다음 \Common7\IDE\Extensions에 파일을 설치 합니다.  
  
3.  .Pkgdef 파일을 엽니다.  
  
4.  다음을 추가 하 여 hklm 기본 시작 페이지를 설정 하려면.pkgdef 수정 여기서 *MyStartPage.xaml* 시작 페이지를 포함 하는.xaml 파일의 이름입니다.  
  
     [$RootKey$ \StartPage\Default]  
  
     "Uri"="$PackageFolder$\\*MyStartPage.xaml*"  
  
     이 시각적 서 새 시작 페이지 위치에서 찾을 값을 알려줍니다.  
  
## <a name="file-copy-deployment"></a>파일 복사 배포  
 사용자 지정 시작 페이지를 배포 하는.vsix 파일을 만들 필요가 없습니다. 대신, 사용자의 \StartPages\ 폴더에 직접 태그 및 지원 파일을 복사할 수 있습니다. **시작 페이지 사용자 지정** 목록에 **시작** 옵션 페이지에는 모든.xaml 파일의 경로 함께 해당 폴더에 나열-예를 들어 %USERPROFILE%\My Documents\Visual Studio  *버전*\StartPages\\*파일 이름*.xaml입니다. 시작 페이지에서 전용 어셈블리에 대 한 참조를 포함 하는 경우 복사 하며 \PrivateAssemblies\ 폴더에 붙여 넣습니다.  
  
 배포 하려면 패키징 없이 만든 시작 페이지.vsix 파일에 좋습니다 기본 파일 복사 전략을 사용 하 여, 예를 들어 일괄 처리 스크립트 또는 수 있는 다른 배포 기술을 파일을 저장할 필요한 디렉터리에 있습니다.  
  
#### <a name="to-manually-install-a-custom-start-page"></a>사용자 지정 시작 페이지를 수동으로 설치 하려면  
  
1.  함께 어셈블리 이외의 모든 지원 파일 페이지 시작 태그를 포함 하는.xaml 파일을 복사 하 고 사용자의 \StartPages\ 폴더에 붙여 넣습니다.  
  
2.  시작 페이지에서는 어셈블리가 어셈블리를 복사 및 붙여 넣을에... \\ *Visual Studio 설치 폴더*\Common7\IDE\PrivateAssemblies\\합니다.  
  
3.  에 **시작 페이지 사용자 지정** 목록에 **시작** 옵션 페이지에서 새 시작 페이지를 선택 합니다. 자세한 내용은 [시작 페이지 사용자 지정](../ide/customizing-the-start-page-for-visual-studio.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [시작 페이지 사용자 지정](../ide/customizing-the-start-page-for-visual-studio.md)   
 [시작 페이지에 사용자 컨트롤 추가](../extensibility/adding-user-control-to-the-start-page.md)