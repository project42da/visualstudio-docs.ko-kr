---
title: "고유한 시작 페이지 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "시작 페이지 만들기"
  - "사용자 지정 시작 페이지"
  - "시작 페이지 사용자 지정"
ms.assetid: a0df5b9c-0932-4e54-86f0-28530ad9d684
caps.latest.revision: 22
caps.handback.revision: 22
manager: "douge"
---
# 고유한 시작 페이지 만들기
시작 페이지 프로젝트 템플릿을 사용하거나 빈 시작 페이지를 만들어 사용자 지정 시작 페이지를 만들 수 있습니다.  
  
 XAML 디자이너는 Visual Studio 응용 프로그램 모델에 대한 종속성으로 인해 사용자 지정 시작 페이지의 시각적 표시를 완전히 정확하게 제공할 수 없습니다.  
  
## 프로젝트 템플릿 사용  
 시작 페이지 프로젝트 템플릿은 Visual Studio 시작 페이지의 전체 복사본인 시작 페이지 프로젝트를 만듭니다. 그런 다음 시작 페이지를 사용자 사양에 맞게 편집할 수 있습니다.  
  
#### 시작 페이지 프로젝트 템플릿을 사용하여 사용자 지정 시작 페이지를 만들려면  
  
1.  Visual Studio 갤러리에서 [시작 페이지 프로젝트 템플릿](http://go.microsoft.com/fwlink/?LinkId=186204)을 다운로드 및 설치합니다.  
  
    > [!WARNING]
    >  이번에는 Visual Studio 2010 시작 페이지 프로젝트 템플릿이 업그레이드되지 않았습니다. 이 템플릿을 업그레이드하는 방법에 대한 자세한 내용은 [방법: Visual Studio 사용자 지정 시작 페이지 업그레이드](../misc/how-to-upgrade-a-visual-studio-custom-start-page.md)를 참조하세요.  
  
2.  템플릿을 설치한 후 해당 템플릿으로 새 시작 페이지 프로젝트를 만듭니다.  
  
3.  새 프로젝트 대화 상자의 왼쪽 창에서 **설치된 템플릿** 아래의 **기타 프로젝트 형식** 노드를 확장하고 **확장성**을 클릭합니다.  
  
4.  가운데 창에서 **사용자 지정 시작 페이지**를 클릭하고 프로젝트 이름을 지정한 다음 **확인**을 클릭합니다.  
  
     Visual Studio에서 Visual Studio 시작 페이지의 전체 복사본인 시작 페이지 프로젝트를 만듭니다.  
  
5.  **솔루션 탐색기**에서 **StartPage.xaml**을 엽니다.  
  
6.  StartPage.xaml을 편집합니다.  
  
     F5 키를 눌러 사용자 지정 시작 페이지가 설치된 Visual Studio의 실험적 인스턴스를 열면 작업을 볼 수 있습니다.  
  
## 빈 시작 페이지 만들기  
 빈 시작 페이지를 만드는 가장 쉬운 방법은 시작 페이지 프로젝트 템플릿을 사용한 다음 콘텐츠를 제거하는 것입니다.  
  
#### 시작 페이지 프로젝트 템플릿을 사용하여 빈 시작 페이지를 만들려면  
  
1.  이전 절차에서 설명한 대로 시작 페이지 프로젝트 템플릿을 사용하여 시작 페이지 프로젝트를 만듭니다.  
  
2.  StartPage.xaml을 엽니다.  
  
3.  .xaml 파일이 다음 예제와 같도록 외부 xml 요소 및 포함하는 그리드 <xref:System.Windows.Controls.Grid> 요소만 남기고 페이지 콘텐츠를 모두 제거합니다.  
  
     [!CODE [BlankStartPage#01](../CodeSnippet/VS_Snippets_VSSDK/blankstartpage#01)]  
  
4.  사용하지 않으려는 지원 파일을 모두 제거합니다.  
  
     배포를 위해 .vsix 및 .pkgdef 파일을 유지해야 합니다.  
  
 또는 Visual Studio에서 인식할 수 있도록 올바른 태그 구조를 가진 XAML 파일을 만들어 빈 시작 페이지를 만들 수 있습니다. 그런 다음 태그와 코드 숨김을 추가하여 원하는 모양과 기능을 얻을 수 있습니다. 자세한 내용은 [사용자 지정 시작 페이지 만들기](../extensibility/creating-a-custom-start-page.md)을 참조하세요.  
  
## 사용자 지정 시작 페이지 테스트 및 적용  
 충돌하지 않는 것을 확인할 때까지 사용자 지정 시작 페이지를 실행할 기본 인스턴스를 설정하지 마세요. 사용자 지정 시작 페이지를 테스트한 경우 Visual Studio의 기본 인스턴스에서 이 절차의 마지막 세 단계를 반복하여 시스템에 적용할 수 있습니다.  
  
#### 사용자 지정 시작 페이지를 테스트하려면  
  
1.  F5 키를 누릅니다.  
  
     새 시작 페이지로 설치되었지만 선택되지 않은 상태로 Visual Studio의 실험적 인스턴스가 열립니다.  
  
2.  Visual Studio의 실험적 인스턴스에서 **도구** 메뉴의 **옵션**을 클릭합니다.  
  
3.  **옵션** 대화 상자의 **환경**에서 **시작**을 선택합니다. 그런 다음 **시작 페이지 사용자 지정** 목록에서 .xaml 파일을 선택하고 **확인**을 클릭합니다.  
  
4.  **보기** 메뉴에서 **시작 페이지**를 클릭합니다.  
  
     작동하는 시작 페이지가 표시됩니다. 새 변경 내용을 확인하려면 실험적 인스턴스를 닫고 변경된 파일을 다시 복사한 다음 실험적 인스턴스를 다시 열어야 합니다.  
  
 bin\\debug 디렉터리의 .vsix 파일을 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847) 웹 사이트나 다른 웹 사이트 또는 인트라넷 공유에 업로드하여 사용자 지정 시작 페이지를 공유할 수 있습니다. 자세한 내용은 [사용자 지정 시작 페이지를 배포합니다.](../extensibility/deploying-custom-start-pages.md)을 참조하세요.  
  
## 참고 항목  
 [시작 페이지 사용자 지정](../ide/customizing-the-start-page-for-visual-studio.md)   
 [연습: 시작 페이지 사용자 지정 XAML에 추가](../extensibility/walkthrough-adding-custom-xaml-to-the-start-page.md)