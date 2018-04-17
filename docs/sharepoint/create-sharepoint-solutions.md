---
title: SharePoint 솔루션 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 807fa532961edb4f2723858a47dcf1fe87134338
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="create-sharepoint-solutions"></a>SharePoint 솔루션 만들기
  SharePoint 응용 프로그램을 SharePoint Designer에서 만드는 대신 Visual Studio에서 만들 수 있습니다. Visual Studio에서는 고급 디버깅 도구, IntelliSense, 문 완성, 프로젝트 템플릿 등의 기능이 제공되므로 SharePoint 개발을 신속하게 수행할 수 있습니다. 또한 Visual Studio는 고급 .NET Framework 기반 도구 및 언어를 활용합니다. Visual Basic 또는 Visual C#을 사용하여 SharePoint 프로젝트를 개발할 수 있으며 JavaScript를 사용하여 SharePoint 프로젝트용 앱을 개발할 수 있습니다.  
  
 SharePoint 2013 및 SharePoint 추가 기능에 대한 자세한 내용은 [SharePoint 2013](http://msdn.microsoft.com/library/jj162979.aspx) 및 [SharePoint용 앱 빌드](http://msdn.microsoft.com/library/office/apps/jj163230%28v=office.15%29.aspx)를 참조하세요.  
  
> [!NOTE]  
>  새 [SharePoint 추가 기능 모델](https://msdn.microsoft.com/library/office/fp179930.aspx) 을 사용하여 사용자를 위한 SharePoint 환경을 확장하는 방법을 알아봅니다. 이러한 추가 기능은 SharePoint 솔루션에 비해 차지하는 공간이 매우 적으며 HTML5, JavaScript, CSS3, XML 등 거의 모든 웹 프로그래밍 기술을 사용하여 빌드할 수 있습니다.  
  
|||  
|-|-|  
|![설명서](../sharepoint/media/vs-icon-documentation.gif "설명서")|**문서**<br /><br /> -   [시작 하기 &#40;Visual Studio에서 SharePoint 개발&#41;](../sharepoint/getting-started-sharepoint-development-in-visual-studio.md)<br />-   [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)<br />-   [SharePoint 솔루션 지역화](../sharepoint/localizing-sharepoint-solutions.md)<br />-   [SharePoint 솔루션 빌드 및 디버깅](../sharepoint/building-and-debugging-sharepoint-solutions.md)<br />-   [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)<br />-   [Visual Studio에서 SharePoint 도구 확장](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)|  
|![설명서](../sharepoint/media/vs-icon-documentation.gif "설명서")|**주요 작업**<br /><br /> -   [연습: 사이트 열, 콘텐츠 형식 및 SharePoint에 대 한 목록 만들기](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)<br />-   [방법: 이벤트 수신기 만들기](../sharepoint/how-to-create-an-event-receiver.md)<br />-   [방법: BDC 모델 만들기](../sharepoint/how-to-create-a-bdc-model.md)<br />-   [방법: SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part.md)<br />-   [방법: SharePoint 응용 프로그램 페이지에 대 한 사용자 정의 컨트롤 만들기 또는 웹 파트](../sharepoint/how-to-create-a-user-control-for-a-sharepoint-application-page-or-web-part.md)|  
|![연습](../sharepoint/media/vs-icon-walkthroughs.gif "연습")|**연습**<br /><br /> -   [SharePoint 개발 연습](../sharepoint/sharepoint-development-walkthroughs.md)|  
|![코드 샘플](../sharepoint/media/vs-icon-codesamples.gif "코드 샘플")|**코드 샘플**<br /><br /> -   [SharePoint 개발 샘플](../sharepoint/sharepoint-development-samples.md)<br />-   [SharePoint 개발자 다운로드](http://msdn.microsoft.com/sharepoint/aa905690.aspx)|  
|![학습](../sharepoint/media/vs-icon-training.gif "학습")|**교육**<br /><br /> -   [SharePoint 개발에 알아봅니다](http://msdn.microsoft.com/sharepoint/aa905692.aspx)|  
|![포럼](../sharepoint/media/vs-icon-forums.gif "포럼")|**포럼**<br /><br /> -   [Visual Studio에서 SharePoint 개발](http://social.msdn.microsoft.com/Forums/vssharepointdevelopment/threads)<br />-   [SharePoint 2010](http://social.msdn.microsoft.com/Forums/category/sharepoint2010,sharepoint/)|  
|![학습](../sharepoint/media/vs-icon-training.gif "학습")|**블로그**<br /><br /> -   [Visual Studio SharePoint 개발 블로그](http://blogs.msdn.com/b/vssharepointtoolsblog/)|  
|![어떻게 할까요? 비디오](../sharepoint/media/vs-icon-howdoivideos.gif "어떻게 할까요? 비디오")|**어떻게 할까요? 비디오**<br /><br /> -   [방법: SharePoint 2010 용 시각적 웹 파트에서에서 만들기 Visual Studio 2010?](http://msdn.microsoft.com/vstudio/ff623014.aspx)<br />-   [방법: Visual Studio 2010에서 SharePoint 2010용 콘텐츠 형식 만들기](http://msdn.microsoft.com/vstudio/ff623016.aspx)<br />-   [방법: Visual Studio 2010에서 SharePoint 2010용 사이트 정의 만들기](http://msdn.microsoft.com/vstudio/ff623012.aspx)<br />-   [방법: Visual Studio 2010을 사용하여 SharePoint 2010용 비즈니스 데이터 연결 모델 만들기](http://msdn.microsoft.com/vstudio/ff623022.aspx)|  
|![채널 9 비디오](../sharepoint/media/vs-icon-channel9videos.gif "Channel 9 비디오")|**채널 9 비디오**<br /><br /> -   [Visual Studio 2010에서 SharePoint 개발 개요](http://channel9.msdn.com/posts/funkyonex/Overview-of-SharePoint-Development-in-Visual-Studio-2010/)<br />-   [Visual Studio 2010을 사용한 SharePoint 2010 웹 파트 빌드 모범 사례](http://channel9.msdn.com/posts/funkyonex/Best-Practices-on-Building-SharePoint-2010-Web-Parts-with-Visual-Studio-2010/)<br />-   [Visual Studio 2010의 SharePoint 기능 및 패키지 디자이너](http://channel9.msdn.com/posts/funkyonex/SharePoint-Feature-and-Package-Designers-in-Visual-Studio-2010/)|  
|![MSDN 개발자 센터](../sharepoint/media/vs-icon-msdndevcenter.gif "MSDN 개발자 센터")|**MSDN 개발자 센터**<br /><br /> -   [Visual Studio 개발 센터](http://msdn.microsoft.com/vstudio/default.aspx)<br />-   [SharePoint 개발자 센터](http://msdn.microsoft.com/sharepoint/default.aspx)<br />-   [SharePoint Server 개발자 센터](http://msdn.microsoft.com/office/aa905503.aspx)<br />-   [SharePoint Designer 개발자 센터](http://msdn.microsoft.com/office/bb421303.aspx)<br />-   [ASP.NET 개발자 센터](http://msdn.microsoft.com/aa336522.aspx)|  
|![사용자 의견 제공](../sharepoint/media/vs-icon-feedback.gif "사용자 의견 제공")|**사용자 의견 제공**<br /><br /> Visual Studio 관련 의견 보내기<br /><br /> -   [Microsoft Connect](http://go.microsoft.com/fwlink/?LinkID=150463)<br /><br /> Visual Studio용 설명서 관련 의견 보내기<br /><br /> -   **Lightweight 보기입니다.** 항목 윗부분에서 **이 항목 평가** 링크를 선택하여 해당 항목 아래쪽으로 이동한 다음 **이 페이지가 유용했습니까?** 라는 질문에 대해 **예** 또는 **아니요** 를 지정할 수 있습니다. **예**를 선택하면 표시되는 확인란 중 하나를 선택하거나 텍스트 상자에 추가 의견을 입력하거나 두 작업을 모두 수행할 수 있습니다. 작업을 완료한 후 **전송** 단추를 선택합니다.<br />-   **ScriptFree 보기.** 항목의 위쪽에서 **의견** 링크를 선택하여 MSDN, TechNet 및 Expression 라이브러리 의견 포럼에서 의견을 제시할 수 있습니다.<br />-   **클래식 보기.** 항목의 위쪽에서 **클릭하여 평가 및 의견 제공** 아이콘을 선택하여 항목에 대한 의견을 설명서 팀에 제공할 수 있습니다.|  
  
  