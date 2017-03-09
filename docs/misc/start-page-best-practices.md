---
title: "시작 페이지 모범 사례 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "시작 페이지 팁"
  - "시작 페이지 모범 사례"
  - "시작 페이지 디자인"
ms.assetid: f6ce1ce0-746e-4004-a37f-6f176f6f5851
caps.latest.revision: 16
caps.handback.revision: 16
manager: "douge"
---
# 시작 페이지 모범 사례
시작 페이지는 Visual Studio 명령에 액세스할 수 있고 Visual Studio가 로드될 때마다 열리기 때문에 사용 또는 배포하기 전에 사용자 지정 시작 페이지의 안전성을 확보하는 것이 좋습니다. 이 항목은 강력한 시작 페이지 디자인을 위한 모범 사례를 제안하고 유용한 UI\(사용자 인터페이스\)를 만드는 방법에 대한 지침이 포함되어 있습니다.  
  
## 안정성 지침  
  
### 리소스 가용성  
 강력한 사용자 지정 시작 페이지를 만들 때 가장 중요한 고려 사항은 필요한 모든 리소스를 사용할 수 있는지 확인하는 것입니다.  
  
-   모든 필수 패키지가 설치되어 있습니다.  
  
-   패키지가 미리 로드되어 있습니다.  
  
-   필요한 모든 어셈블리가 \\PrivateAssemblies\\ 폴더에 있습니다.  
  
-   네트워크 또는 인터넷 연결을 사용하는 모든 구성 요소에 오프라인 시나리오 및 끊어진 연결을 위한 대체 경로가 있습니다.  
  
### 성능  
 시작 페이지에서 큰 메모리 요구 사항이 있거나 많은 리소스를 로드하는 경우 시작 성능이 어떻게 영향을 받는지 고려합니다. 시작 시간이 크게 늘어나지 않도록 실제 환경인 경우 백그라운드에서 또는 요청 시 구성 요소를 로드하도록 이러한 시작 페이지를 프로그래밍합니다.  
  
### 개발 프로세스  
 활성 시작 페이지를 직접 수정하는 경우 실수로 오류가 생겨서 Visual Studio 작동이 중단될 수 있습니다. Visual Studio가 열릴 때마다 시작 페이지가 열리기 때문에 중단되는 시작 페이지를 수정하는 것은 어렵습니다. 따라서 안정성을 위해 시작 페이지 파일의 복사본을 수정하고 Visual Studio의 실험적 인스턴스에서 테스트하는 것이 좋습니다. 새로운 시작 페이지가 안정되면 Visual Studio의 기본 인스턴스에서 실행되도록 설정할 수 있습니다.  
  
> [!NOTE]
>  또한 기본 인스턴스에 사용하기 전에 Visual Studio의 실험적 인스턴스에서 모든 타사 시작 페이지를 테스트하는 것이 좋습니다.  
  
##### Visual Studio의 실험적 인스턴스에서 시작 페이지를 테스트하려면  
  
1.  시작 페이지 프로젝트 템플릿을 사용하는 경우 F5 키를 누릅니다. 그렇지 않은 경우는 다음과 같습니다.  
  
    1.  .xaml 파일 및 지원 텍스트 또는 태그를 \\%USERPROFILE%\\My Documents\\Visual Studio *\<version\>*\\StartPages\\에 복사합니다.  
  
    2.  필요한 모든 어셈블리를 *\<Visual Studio 설치 경로\>*\\Common7\\IDE\\PrivateAssemblies\\에 복사합니다.  
  
    3.  Visual Studio 명령 프롬프트에서 다음 명령을 사용하여 Visual Studio의 실험적 인스턴스를 엽니다.  
  
         **Devenv \/rootsuffix exp**  
  
2.  **도구** 메뉴에서 **옵션**을 클릭합니다.**환경**을 선택한 다음 **시작**을 선택합니다.**시작 페이지 사용자 지정** 목록에서 이름을 바꾼 StartPage.xaml 파일을 선택하고 **확인**을 클릭합니다.  
  
3.  **보기** 메뉴에서 **시작 페이지**를 클릭합니다.  
  
     사용자 지정 시작 페이지가 열립니다. 수정하는 시작 페이지가 중단되는 경우 사용자 지정 시작 페이지를 계속 수정할 수 있도록 Visual Studio의 기본 인스턴스를 다시 시작하고 필요한 내용을 수정한 다음 다른 실험적 인스턴스를 엽니다.  
  
 시작 페이지에서 Visual Studio의 기본 인스턴스가 중단되는 경우 HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\14.0\\StartPage\\Default\\CustomizationEnabled의 레지스트리 값을 0으로 설정하여 사용자 지정 시작 페이지를 임시로 사용하지 않도록 설정할 수 있습니다. 또는 현재 기본 시작 페이지의 .xaml 파일 이름을 임시로 바꿀 수 있습니다. 둘 중 어떤 조치를 취하든 Visual Studio를 열어 둔 상태로 오류를 계속 수정할 수 있습니다.  
  
### 디버깅  
 시작 페이지가 처음으로 로드될 때 시작 페이지 도구 창이 예외를 catch하지만 그 이후에는 예외를 catch하지 않습니다. 다음 레지스트리 값을 "1"로 설정하면 Visual Studio가 모든 처리되지 않은 예외를 표시하도록 할 수 있습니다.  
  
 HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\14.0\\General\\EnableUnhandledExceptionDisplay  
  
 예외 정보는 메시지 상자에 표시되어 시작 페이지 또는 다른 처리되지 않은 위치, 심지어 기본 Visual Studio 인스턴스에서도 컨트롤을 디버그할 수 있습니다. 예외가 발생한 후 디버그할 수 없는 경우 "devenv \/safemode" 명령을 사용하여 Visual Studio를 다시 시작하고 이전 시작 페이지로 다시 돌아가면 실험적 인스턴스에서 디버깅을 계속할 수 있습니다.  
  
### 상대 경로  
 시작 페이지에서 파일 경로를 참조할 때는 서로 다른 시스템 구성을 허용하기 위해 언제나 상대 경로를 사용합니다. 그러나 시작 페이지의 모든 상대 경로 루트는 \\StartPages\\ 폴더가 아닌 \\*Visual Studio 설치 폴더*\\Common7\\IDE가 되며 이 폴더에 devenv.exe가 있습니다. \\StartPages\\ 폴더에 상대적인 경로를 설정하려면 VS 시작 페이지 상대 변환기를 사용합니다. 이렇게 하려면 다음 예제처럼 개체의 `Source` 속성을 `vs:StartPageRelative`로 설정합니다.  
  
 XAML  
  
```  
<Image Source="{vs:StartPageRelative myImage.png}" .../>  
```  
  
 Visual Studio에 포함된 리소스 또는 다른 패키지에 포함된 파일에 액세스할 때 표준 상대 경로 구문을 사용합니다.  
  
### 배포  
 다른 사용자에게 사용자 지정 시작 페이지를 배포할 때 다음 모범 사례를 권장합니다.  
  
#### 사용자 설정  
  
-   사용자 설정을 준수합니다. 기존 시작 페이지 기본 설정을 덮어쓰지 않습니다.  
  
#### VSIX  
 다음 사례를 VSIX 배포에 적용합니다.  
  
-   VSIX 매니페스트의 [GettingStartedGuide](http://msdn.microsoft.com/ko-kr/261bb1fd-abae-4ed6-80a8-90d5fc3bb8c6) 요소를 사용하여 기본 시작 페이지를 설정하는 방법에 대한 지침을 가리킵니다.  
  
-   VSIX 매니페스트의 [Name](http://msdn.microsoft.com/ko-kr/d99d38d1-060b-401a-9b9f-ede2c6213a11) 요소 및 [Description](http://msdn.microsoft.com/ko-kr/24ddc57e-e991-4a43-b0c9-0e76da293e99) 요소를 사용하여 확장을 시작 페이지로 명확하게 식별하고 목적을 설명합니다.  
  
-   VSIX 매니페스트에 절대 경로가 포함되지 않았는지 확인합니다.  
  
-   [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847) 웹 사이트에 업로드하는 경우 사용자가 확장을 시작 페이지로 식별할 수 있도록 관련 태그를 포함합니다.  
  
#### MSI  
 Windows Installer\(MSI\) 패키지에서 배포하는 더 큰 확장의 일부로 시작 페이지를 생성하는 경우 시작 페이지가 대상 컴퓨터의 기본 시작 페이지로 설치되도록 설정할 수 있습니다. 이렇게 하려면 시작 페이지 .xaml 파일의 이름을 HKCU\\Software\\Microsoft\\VisualStudio\\14.0\\StartPage\\Default\\ 레지스트리 키의 URI 값으로 작성합니다. 이 레지스트리 값을 설정하는 경우 다음 지침을 사용합니다.  
  
-   설치 관리자에서 사용자가 새 시작 페이지를 기본값으로 설정할지 여부를 선택할 수 있도록 UI를 제공합니다.  
  
-   사용자가 확장을 제거하면 이전 레지스트리 값을 복원합니다.  
  
### WPF\(Windows Presentation Framework\)  
 XAML 태그는 WPF 모범 사례를 준수해야 합니다. 응용 프로그램 개발을 위한 [!INCLUDE[TLA#tla_winclient](../misc/includes/tlasharptla_winclient_md.md)] 및 [!INCLUDE[TLA#tla_netframewk](../misc/includes/tlasharptla_netframewk_md.md)] 모범 사례에 대한 자세한 내용은 다음 항목을 적절하게 참조하세요.  
  
|영역|항목|  
|--------|--------|  
|접근성|[Accessibility Best Practices](../Topic/Accessibility%20Best%20Practices.md)|  
|지역화|[WPF 전역화 및 지역화 개요](../Topic/WPF%20Globalization%20and%20Localization%20Overview.md)|  
|성능|[WPF 응용 프로그램 성능 최적화](../Topic/Optimizing%20WPF%20Application%20Performance.md)|  
|보안|[보안\(WPF\)](../Topic/Security%20\(WPF\).md)|  
  
## 사용자 인터페이스 지침  
 시작 페이지에 대한 편리하고 직관적인 사용자 환경을 보장하려면 해당하는 다음 UI 지침을 사용합니다.  
  
### 상위 행  
  
#### 배너  
  
-   배너 이미지의 높이는 이를 포함하는 행의 행 높이 정의와 동일하게 만듭니다.  
  
-   다양한 창 크기 및 화면 해상도에 맞게 조정하기 위해 배너 이미지를 어떤 너비에서든지 만족스럽게 보이도록 만듭니다.  
  
-   배너 영역을 깔끔하게 유지합니다. 추가 단추 또는 그래픽으로 로고를 오버레이하지 마세요.  
  
### 왼쪽 열  
  
#### 단추 영역  
  
-   최근 프로젝트의 이름을 표시할 여유가 있도록 가장 많이 사용하는 컨트롤만 단추 영역에 넣습니다. 단추를 5개 미만으로 하는 것이 좋습니다.  
  
#### 최근에 사용한 프로젝트  
  
-   이 컨트롤을 사용하면 사용자가 최근 프로젝트에 액세스하도록 합니다. 0개에서 24개까지 표시할 프로젝트 수를 설정할 수 있습니다. 이 UI는 시작 페이지에서 가장 자주 사용하는 섹션이므로 제거하지 않는 것이 좋습니다.  
  
#### 시작 페이지 옵션  
  
-   **프로젝트 로드 후 페이지 닫기** 및 **시작할 때 페이지 표시** 옵션이 시작 페이지에 나타나는지 확인합니다.  
  
-   이 영역의 추가 컨트롤을 위해 확인란 또는 라디오 단추를 사용하고 컨트롤이 시작 페이지 기본 설정과 관련이 있는지 확인하는 것이 좋습니다.  
  
### 콘텐츠 영역  
  
#### 최상위 탭  
  
-   일반적인 화면 너비에서 탭 컨트롤이 래핑될 만큼 많은 탭을 추가하지 않도록 합니다.  
  
-   탭에 대한 간단한 설명이 포함된 이름을 사용합니다.  
  
-   탭이 그룹화된 콘텐츠 영역을 나타내도록 합니다.  
  
#### 하위 수준 탭  
  
-   세 개 이상의 하위 항목이 있는 경우에만 하위 수준 탐색을 사용합니다.  
  
-   일반적인 화면 너비에서 탭 컨트롤이 래핑될 만큼 많은 탭을 추가하지 않도록 합니다.  
  
-   탭에 대한 간단한 설명이 포함된 이름을 사용합니다.  
  
#### 하위 수준 탭 콘텐츠  
  
-   하위 수준 탭에 5개 이하의 콘텐츠 항목을 표시합니다.  
  
#### 항목 내용  
  
-   콘텐츠 항목당 4개 이하의 링크를 표시합니다.  
  
-   이미지를 콘텐츠 항목과 연결하는 경우 모든 이미지가 175x125 픽셀인지 확인합니다.  
  
-   콘텐츠 항목에 대한 간단한 설명이 포함된 제목을 사용합니다.  
  
-   콘텐츠 항목의 설명은 두 문장 이하로 제한합니다.  
  
### 일반  
  
#### 애니메이션  
  
-   애니메이션을 사용하는 경우 0.5초 이하로 제한하면 성능 저하를 인지하지 못할 수 있습니다.  
  
#### 환경 색  
  
-   글꼴 및 색에 대한 시스템 설정을 준수합니다.  
  
-   밝은 색 배경을 사용합니다.  
  
-   원격 세션에서 부드럽게 색상이 저하되도록 원격 데스크톱 검색을 사용합니다.  
  
## 참고 항목  
 [시작 페이지 아키텍처](../misc/start-page-architecture.md)   
 [사용자 지정 시작 페이지를 배포합니다.](../extensibility/deploying-custom-start-pages.md)   
 [시작 페이지에 Visual Studio 명령 추가](../extensibility/adding-visual-studio-commands-to-a-start-page.md)