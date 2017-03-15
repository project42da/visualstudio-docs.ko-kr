---
title: "사용자 지정 시작 페이지를 배포합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "패키지 시작 페이지"
  - "시작 페이지를 배포 합니다."
ms.assetid: 4a7eb360-de83-41d5-be53-3cfb160d19f9
caps.latest.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 21
---
# 사용자 지정 시작 페이지를 배포합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSIX 배포를 사용 하 여 또는 대상 컴퓨터에 올바른 위치에 파일을 복사 하 여 사용자 지정 시작 페이지를 배포할 수 있습니다.  
  
## 시작 페이지 프로젝트 템플릿을 사용 하 여 VSIX 배포  
 시작 페이지 프로젝트 템플릿을 사용 하 여 시작 페이지를 만들 후 프로젝트를 빌드할 때 Visual Studio는 배포할 수 있는.vsix 파일을 만듭니다. 패키징.vsix 파일에는 시작 페이지 사용자에 따라 배포에 대 한 다음 옵션을 제공 합니다.  
  
-   공용 웹 사이트에서 또는 네트워크 공유에서.vsix 파일을 넣을 수 있습니다. 파일을 열 때 시작 페이지는 자동으로 설치 됩니다.  
  
-   .Vsix 파일을 업로드할 수는 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847) 웹 사이트 사용자가 사용 하 여 설치할 수 있도록 **확장 관리자**합니다.  
  
 시작 페이지 프로젝트 템플릿은 복사본을 수정 하 고 원래 유지할 수 있도록 기본 Visual Studio 시작 페이지의 복사본을 만듭니다.  
  
 시작 페이지 프로젝트 템플릿을 사용 하 여 얻을 수 있습니다 **확장 관리자** 하거나 웹 사이트에서 다운로드 합니다.  
  
## 시작 페이지 프로젝트 템플릿을 사용 하지 않고 VSIX 배포  
 VSIX 배포 하는 데 필요한 VSIX 등록 과정에서 인식 되는 폴더에 설치할 수에 대 한 확장 **확장 관리자**합니다. 시작 페이지 프로젝트 템플릿을 이미 올바른 폴더를 지정 하므로 패키지 VSIX 배포에 대 한 확장 하려고 할 때마다 사용 하는 것이 좋습니다. 그러나 서식 파일을 사용할 수 없습니다 사례를 설정한 경우 사용 하지 않고 VSIX 배포를 만들 수 있습니다.  
  
 시작 페이지 프로젝트 템플릿을 사용 하지 않고 VSIX 배포를 만들려면 먼저이 두 가지 방법 중 하나로 시작 페이지에 대 한.vsix 파일을 만듭니다.  
  
-   빈 VSIX 프로젝트에 사용자 지정 시작 페이지 파일을 추가 합니다. 자세한 내용은 [VSIX 프로젝트 템플릿](../extensibility/vsix-project-template.md)을 참조하세요.  
  
-   .Vsix 파일을 수동으로 만듭니다. 자세한 내용은 [방법: 수동으로 확장 패키지\(VSIX 배포\)](../misc/how-to-manually-package-an-extension-vsix-deployment.md)을 참조하십시오.  
  
 Visual studio 시작 페이지를 인식할 수는 `Content Element` VSIX 매니페스트 있어야는 `CustomExtension Element` 있는 `Type` 특성으로 설정 `"StartPage"`합니다. VSIX 배포를 사용 하 여 설치 된 시작 페이지 확장에 표시 된 **시작 페이지 사용자 지정** 목록에서 **시작** 옵션으로 페이지 **\[설치 된 확장\]** *확장 이름*합니다.  
  
 시작 페이지 패키지 어셈블리를 포함 하는 경우 Visual Studio를 시작할 때 사용할 수 있도록 바인딩 경로 등록을 추가 해야 합니다. 이 위해 패키지에는 다음 정보가 포함 하는.pkgdef 파일에 포함 해야 합니다.  
  
```  
[$RootKey$\BindingPaths\{Insert a new GUID here}]  
"$PackageFolder$"=""  
```  
  
### 모든 사용자에 대 한 VSIX 배포  
 기본적으로 VSIX 패키지에 배포 된 확장 프로그램은 현재 사용자에 대해서만 설치 합니다. 모든 사용자가 배포를 만들어 대상 컴퓨터의 모든 사용자에 대 한 설치 하는 시작 페이지를 만들 수 있습니다.  
  
##### 모든 사용자가 배포를 만들려면  
  
1.  코드 보기에서 extension.vsixmanifest 파일을 엽니다.  
  
2.  에 `Identifier` vsix 매니페스트의 요소 추가 `AllUsers` 의 값을 갖는 요소가 `true`합니다.  
  
    ```  
    <AllUsers>true</AllUsers>  
    ```  
  
     그러면 vsix 설치 관리자를 관리자 권한으로 메시지를 표시 하 고 다음 \\Common7\\IDE\\Extensions에 파일을 설치 합니다.  
  
3.  .Pkgdef 파일을 엽니다.  
  
4.  HKLM에서 기본 시작 페이지에서 다음을 추가 하 여 설정 하는.pkgdef 수정 여기서 *MyStartPage.xaml* 시작 페이지를 포함 하는.xaml 파일의 이름입니다.  
  
     \[$RootKey$ \\StartPage\\Default\]  
  
     "Uri"\="$PackageFolder$ \\*MyStartPage.xaml*"  
  
     이렇게 하면 새 페이지 시작 위치를 확인 하는 시각적 겨 됩니다.  
  
## 파일 복사 배포  
 사용자 지정 시작 페이지를 배포 하기 위한.vsix 파일을 만들 필요가 없습니다. 대신, 사용자의 \\StartPages\\ 폴더에 직접 태그 및 지원 파일을 복사할 수 있습니다.**시작 페이지 사용자 지정** 목록에 **시작** 옵션 페이지의 경로 함께 해당 폴더에 있는 모든.xaml 파일을 나열\-%USERPROFILE%\\My Documents\\Visual Studio 예를 들어 *버전*\\StartPages\\*파일 이름*.xaml입니다. 시작 페이지에서 전용 어셈블리에 대 한 참조를 포함 하는 경우 복사를 \\PrivateAssemblies\\ 폴더에 붙여 넣습니다.  
  
 패키징 없이 생성 하는 시작 페이지를 배포 하는.vsix 파일에 좋습니다 예를 들어 수 있는 다른 배포 기술 또는 배치 스크립트를 파일에에서 둡니다 필요한 디렉터리를 기본 파일 복사 전략을 사용 하 합니다.  
  
#### 사용자 지정 시작 페이지를 수동으로 설치 하려면  
  
1.  시작 페이지 태그의 함께 어셈블리 이외의 모든 지원 파일을 포함 하는.xaml 파일을 복사 하 고 사용자의 \\StartPages\\ 폴더에 붙여 넣습니다.  
  
2.  시작 페이지에서 어셈블리를 필요로 하는 경우 복사 하 고에 붙여넣습니다. \\*Visual Studio 설치 폴더*\\Common7\\IDE\\PrivateAssemblies\\ 합니다.  
  
3.  에 **시작 페이지 사용자 지정** 목록에 **시작** 옵션 페이지에서 새로운 시작 페이지를 선택 합니다. 자세한 내용은 [시작 페이지 사용자 지정](../ide/customizing-the-start-page-for-visual-studio.md)을 참조하세요.  
  
## 참고 항목  
 [시작 페이지 사용자 지정](../ide/customizing-the-start-page-for-visual-studio.md)   
 [시작 페이지에 사용자 컨트롤 추가](../extensibility/adding-user-control-to-the-start-page.md)