---
title: "연습: 표시 나타나도록 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - QuickInfo
ms.assetid: 23fb8384-4f12-446f-977f-ce7910347947
caps.latest.revision: "27"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 303ce6608ee17b99995d871c5da1536a08fef335
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-displaying-quickinfo-tooltips"></a>연습: QuickInfo 도구 설명 표시
QuickInfo 메서드 시그니처를 표시 하는 IntelliSense 기능이 이며 사용자 설명을 메서드 이름 위로 포인터를 이동 합니다. QuickInfo 설명을 제공 하려는 식별자를 정의 하 고 다음에 콘텐츠를 표시할 도구 설명을 만들어 QuickInfo 등의 언어 기반 기능을 구현할 수 있습니다. 언어 서비스의 컨텍스트에서 QuickInfo를 정의할 수 있습니다 또는 고유한 파일 이름 확장명 및 콘텐츠 형식을 정의 하 고 해당 형식만 대 한 QuickInfo를 표시할 수 또는 기존 콘텐츠 형식 (예: "text")에 대 한 QuickInfo를 표시할 수 있습니다. 이 연습에서는 QuickInfo "text" 콘텐츠 형식에 대 한 표시 하는 방법을 보여 줍니다.  
  
 이 연습에서 QuickInfo 예제 메서드 이름 위로 포인터를 이동할 때 도구 설명을 표시 합니다. 이 설계에서는 이러한 네 가지 인터페이스를 구현 해야 합니다.  
  
-   소스 인터페이스  
  
-   원본 공급자 인터페이스  
  
-   컨트롤러 인터페이스  
  
-   컨트롤러 공급자 인터페이스  
  
 소스 및 컨트롤러 공급자 프레임 워크 MEF (Managed Extensibility) 구성 요소 부분 이며 원본 및 컨트롤러 클래스 내보내기에 대 한 책임이 가져오기 서비스 브로커와 같은 <xref:Microsoft.VisualStudio.Text.ITextBufferFactoryService>, 도구 설명 텍스트를 만듦 버퍼 및 <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoBroker>, QuickInfo 세션 트리거되어 합니다.  
  
 이 예에서는 QuickInfo 원본은 메서드 이름 및 설명의 하드 코드 된 목록을 사용 하지만 전체 구현에서 언어 서비스 및 해당 언어 설명서에 대 한 책임이 해당 콘텐츠를 제공 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-a-mef-project"></a>MEF 프로젝트 만들기  
  
#### <a name="to-create-a-mef-project"></a>MEF 프로젝트를 만들려면  
  
1.  C# VSIX 프로젝트를 만듭니다. (에 **새 프로젝트** 대화 상자에서 **Visual C# / 확장성**, 다음 **VSIX 프로젝트**.) 솔루션 이름을 `QuickInfoTest`합니다.  
  
2.  편집기 분류자 항목 템플릿을 프로젝트에 추가 합니다. 자세한 내용은 참조 [편집기 항목 템플릿을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-an-editor-item-template.md)합니다.  
  
3.  기존 클래스 파일을 삭제합니다.  
  
## <a name="implementing-the-quickinfo-source"></a>QuickInfo 소스 구현  
 QuickInfo 소스는 식별자와 해당 설명의 집합을 수집 하 고 식별자 중 하나가 발생할 때 도구 설명 텍스트 버퍼에 콘텐츠를 추가 하는 일을 담당 합니다. 이 예제에서는 식별자 및 해당 설명을 보려면 방금 소스 생성자에 추가 됩니다.  
  
#### <a name="to-implement-the-quickinfo-source"></a>QuickInfo 소스를 구현 하려면  
  
1.  클래스 파일을 추가 하 고 이름을 `TestQuickInfoSource`합니다.  
  
2.  Microsoft.VisualStudio.Language.IntelliSense에 대 한 참조를 추가 합니다.  
  
3.  다음 가져오기를 추가 합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_1.vb)]
     [!code-csharp[VSSDKQuickInfoTest#1](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_1.cs)]  
  
4.  구현 하는 클래스 선언 <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSource>, 하 고 이름을 `TestQuickInfoSource`합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_2.vb)]
     [!code-csharp[VSSDKQuickInfoTest#2](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_2.cs)]  
  
5.  메서드 이름 및 메서드 서명을의 집합 및 텍스트 버퍼를 사용 하는, QuickInfo 원본 공급자에 대 한 필드를 추가 합니다. 메서드 이름 및 시그니처가이 예제에서는 초기화는 `TestQuickInfoSource` 생성자입니다.  
  
     [!code-vb[VSSDKQuickInfoTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_3.vb)]
     [!code-csharp[VSSDKQuickInfoTest#3](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_3.cs)]  
  
6.  QuickInfo 소스 공급자와 텍스트 버퍼를 설정 하 고 메서드 이름 및 메서드 서명을 및 설명 집합 정보를 표시 하는 생성자를 추가 합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_4.vb)]
     [!code-csharp[VSSDKQuickInfoTest#4](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_4.cs)]  
  
7.  <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSource.AugmentQuickInfoSession%2A> 메서드를 구현합니다. 이 예제에서는 메서드 커서가 선 또는 텍스트 버퍼의 끝에 있는 경우 현재 단어 또는 이전 단어 찾습니다. 단어가 메서드 이름 중 하나일 경우 해당 메서드 이름에 대 한 설명 QuickInfo 내용에 추가 됩니다.  
  
     [!code-vb[VSSDKQuickInfoTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_5.vb)]
     [!code-csharp[VSSDKQuickInfoTest#5](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_5.cs)]  
  
8.  Dispose () 메서드를 이후 구현도 해야 <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSource> 구현 <xref:System.IDisposable>:  
  
     [!code-vb[VSSDKQuickInfoTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_6.vb)]
     [!code-csharp[VSSDKQuickInfoTest#6](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_6.cs)]  
  
## <a name="implementing-a-quickinfo-source-provider"></a>QuickInfo 소스 공급자 구현  
 QuickInfo 원본의 공급자를 인스턴스화할 QuickInfo 소스 및 MEF 구성 요소 부분으로 자신을 내보낼 데 주로 사용 됩니다. MEF 구성 요소 부분 이기 때문에 다른 MEF 구성 요소 부분을 가져올 수 있습니다.  
  
#### <a name="to-implement-a-quickinfo-source-provider"></a>QuickInfo 소스 공급자를 구현 하려면  
  
1.  명명 된 QuickInfo 소스 공급자를 선언 `TestQuickInfoSourceProvider` 를 구현 하는 <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSourceProvider>, 및 사용 하 여 내보내기는 <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "도구 설명 QuickInfo 원본"의 <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> 의 Before = "default" 및 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "text"입니다.  
  
     [!code-vb[VSSDKQuickInfoTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_7.vb)]
     [!code-csharp[VSSDKQuickInfoTest#7](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_7.cs)]  
  
2.  두 개의 편집기 서비스를 가져올 <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> 및 <xref:Microsoft.VisualStudio.Text.ITextBufferFactoryService>의 속성으로 `TestQuickInfoSourceProvider`합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_8.vb)]
     [!code-csharp[VSSDKQuickInfoTest#8](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_8.cs)]  
  
3.  구현 <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSourceProvider.TryCreateQuickInfoSource%2A> 새 반환할 `TestQuickInfoSource`합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_9.vb)]
     [!code-csharp[VSSDKQuickInfoTest#9](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_9.cs)]  
  
## <a name="implementing-a-quickinfo-controller"></a>QuickInfo 컨트롤러 구현  
 QuickInfo 컨트롤러 QuickInfo를 표시 해야 하는 시기를 결정 합니다. 이 예제에서는 QuickInfo는 포인터가 메서드 이름 중 하나에 해당 하는 단어 위에 있을 때 표시 됩니다. QuickInfo 컨트롤러 QuickInfo 세션을 트리거하는 마우스 가리키기 이벤트 처리기를 구현 합니다.  
  
#### <a name="to-implement-a-quickinfo-controller"></a>QuickInfo 컨트롤러를 구현 하려면  
  
1.  구현 하는 클래스 선언 <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController>, 하 고 이름을 `TestQuickInfoController`합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_10.vb)]
     [!code-csharp[VSSDKQuickInfoTest#10](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_10.cs)]  
  
2.  텍스트 보기, QuickInfo 세션 QuickInfo 컨트롤러 공급자의 표시 텍스트 버퍼 텍스트 보기에 대 한 전용 필드를 추가 합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_11.vb)]
     [!code-csharp[VSSDKQuickInfoTest#11](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_11.cs)]  
  
3.  필드를 설정 하 고 마우스 가리키기 이벤트 처리기를 추가 하는 생성자를 추가 합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_12.vb)]
     [!code-csharp[VSSDKQuickInfoTest#12](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_12.cs)]  
  
4.  QuickInfo 세션을 트리거하는 마우스 가리키기 이벤트 처리기를 추가 합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_13.vb)]
     [!code-csharp[VSSDKQuickInfoTest#13](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_13.cs)]  
  
5.  구현 된 <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController.Detach%2A> 메서드를 컨트롤러 텍스트 보기에서 분리 된 경우 마우스 가리키기 이벤트 처리기를 제거 합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#14](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_14.vb)]
     [!code-csharp[VSSDKQuickInfoTest#14](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_14.cs)]  
  
6.  구현 된 <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController.ConnectSubjectBuffer%2A> 메서드 및 <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController.DisconnectSubjectBuffer%2A> 이 예에서는 빈 메서드로 메서드.  
  
     [!code-vb[VSSDKQuickInfoTest#15](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_15.vb)]
     [!code-csharp[VSSDKQuickInfoTest#15](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_15.cs)]  
  
## <a name="implementing-the-quickinfo-controller-provider"></a>QuickInfo 컨트롤러 공급자 구현  
 QuickInfo 컨트롤러의 공급자 자체 MEF 구성 요소 부분으로 내보내고 인스턴스화할 QuickInfo 컨트롤러를 주로 사용 됩니다. MEF 구성 요소 부분 이기 때문에 다른 MEF 구성 요소 부분을 가져올 수 있습니다.  
  
#### <a name="to-implement-the-quickinfo-controller-provider"></a>QuickInfo 컨트롤러 공급자를 구현 하려면  
  
1.  이라는 클래스를 선언 `TestQuickInfoControllerProvider` 를 구현 하는 <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseControllerProvider>, 및 사용 하 여 내보내기는 <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "도구 설명 QuickInfo 컨트롤러"와 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "text":  
  
     [!code-vb[VSSDKQuickInfoTest#16](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_16.vb)]
     [!code-csharp[VSSDKQuickInfoTest#16](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_16.cs)]  
  
2.  가져오기는 <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoBroker> 속성으로.  
  
     [!code-vb[VSSDKQuickInfoTest#17](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_17.vb)]
     [!code-csharp[VSSDKQuickInfoTest#17](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_17.cs)]  
  
3.  구현 된 <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseControllerProvider.TryCreateIntellisenseController%2A> QuickInfo 컨트롤러를 인스턴스화하여 메서드.  
  
     [!code-vb[VSSDKQuickInfoTest#18](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_18.vb)]
     [!code-csharp[VSSDKQuickInfoTest#18](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_18.cs)]  
  
## <a name="building-and-testing-the-code"></a>코드 빌드 및 테스트  
 이 코드를 테스트 하려면 QuickInfoTest 솔루션을 빌드하고 실험적 인스턴스에서 실행 합니다.  
  
#### <a name="to-build-and-test-the-quickinfotest-solution"></a>빌드하고 QuickInfoTest 솔루션을 테스트 하려면  
  
1.  솔루션을 빌드합니다.  
  
2.  디버거에서 이 프로젝트를 실행하면 Visual Studio의 두 번째 인스턴스가 인스턴스화됩니다.  
  
3.  텍스트 파일 형식 단어를 포함 하는 일부 텍스트 "추가" 및 "빼기"를 만듭니다.  
  
4.  "추가"의 각 항목 중 하나 위에 포인터를 이동 합니다. 서명과에 대 한 설명을 `add` 메서드를 표시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 파일 이름 확장명에 콘텐츠 형식 연결](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)