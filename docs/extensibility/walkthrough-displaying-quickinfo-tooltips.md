---
title: "연습: 요약 정보 도구 설명 표시 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 새-요약 정보"
ms.assetid: 23fb8384-4f12-446f-977f-ce7910347947
caps.latest.revision: 27
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 27
---
# 연습: 요약 정보 도구 설명 표시
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

요약 정보는 메서드 시그니처를 표시 하는 IntelliSense 기능 및 메서드 이름 위로 포인터를 이동 하는 경우 사용자에 대해 설명 합니다. 요약 정보 설명을 제공 하려는 식별자를 정의 하 고 다음에 콘텐츠를 표시할 도구 설명 만들기 요약 정보 등의 언어 기반 기능을 구현할 수 있습니다. 언어 서비스의 컨텍스트에서 요약 정보를 정의할 수 있습니다 고유한 파일 이름 확장명 및 콘텐츠 형식을 정의 하 고 해당 형식만 대 한 요약 정보를 표시 하거나 기존 콘텐츠 형식 \(예: "text"\)에 대 한 요약 정보를 표시할 수 있습니다. 이 연습에서는 "text" 콘텐츠 형식에 대 한 요약 정보를 표시 하는 방법을 보여 줍니다.  
  
 이 연습에서 요약 정보 예제 메서드 이름 위로 포인터를 이동할 때 도구 설명을 표시 합니다. 이 디자인에서는 이러한 네 가지 인터페이스를 구현 해야 합니다.  
  
-   원본 인터페이스  
  
-   원본 공급자 인터페이스  
  
-   컨트롤러 인터페이스  
  
-   컨트롤러 공급자 인터페이스  
  
 소스 및 컨트롤러 공급자 프레임 워크 MEF \(Managed Extensibility\) 구성 요소 부분으로 소스 및 컨트롤러 클래스를 내보낼 담당와 서비스 가져오기 및와 같은 조정는 <xref:Microsoft.VisualStudio.Text.ITextBufferFactoryService>, 도구 설명 텍스트 버퍼 만드는 및 <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoBroker>, 요약 정보 세션의 트리거.  
  
 이 예제에서는 요약 정보 소스 메서드 이름 및 설명의 하드 코드 된 목록을 사용 하지만 전체 구현에서 언어 서비스와 해당 언어 설명서는 해당 콘텐츠를 제공 합니다.  
  
## 사전 요구 사항  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하세요.  
  
## MEF 프로젝트 만들기  
  
#### MEF 프로젝트를 만들려면  
  
1.  C\# VSIX 프로젝트를 만듭니다. \(에 **새 프로젝트** 대화 상자에서 **Visual C\# \/ 확장성**, 다음 **VSIX 프로젝트**.\) 솔루션의 이름을 `QuickInfoTest`합니다.  
  
2.  편집기 분류자 항목 템플릿을 프로젝트에 추가 합니다. 자세한 내용은 [편집기 항목 템플릿을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-an-editor-item-template.md)을 참조하세요.  
  
3.  기존 클래스 파일을 삭제합니다.  
  
## 요약 정보 소스 구현  
 요약 정보 소스는 식별자 및 해당 설명의 집합을 수집 하 고 식별자 중 하나가 발생할 때 도구 설명 텍스트 버퍼에는 콘텐츠를 추가 하는 일을 담당 합니다. 이 예제에서는 식별자 및 해당 설명을 보려면 방금 소스 생성자에 추가 됩니다.  
  
#### 요약 정보 소스를 구현 하려면  
  
1.  클래스 파일을 추가 하 고 이름을 `TestQuickInfoSource`합니다.  
  
2.  Microsoft.VisualStudio.Language.IntelliSense에 대 한 참조를 추가 합니다.  
  
3.  다음 import를 추가 합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_1.vb)]
     [!code-cs[VSSDKQuickInfoTest#1](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_1.cs)]  
  
4.  구현 하는 클래스 선언 <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSource>, 하 고 이름을 `TestQuickInfoSource`합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_2.vb)]
     [!code-cs[VSSDKQuickInfoTest#2](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_2.cs)]  
  
5.  메서드 이름 및 메서드 시그니처의의 집합 및 텍스트 버퍼를 사용 하는, 요약 정보 원본 공급자에 대 한 필드를 추가 합니다. 메서드 이름 및 시그니처와이 예제에서는 초기화는 `TestQuickInfoSource` 생성자입니다.  
  
     [!code-vb[VSSDKQuickInfoTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_3.vb)]
     [!code-cs[VSSDKQuickInfoTest#3](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_3.cs)]  
  
6.  요약 정보 소스 공급자와 텍스트 버퍼를 설정 하 고 메서드 이름 및 메서드 시그니처 및 설명 집합 정보를 표시 하는 생성자를 추가 합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_4.vb)]
     [!code-cs[VSSDKQuickInfoTest#4](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_4.cs)]  
  
7.  <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSource.AugmentQuickInfoSession%2A> 메서드를 구현합니다. 이 예제에서는 메서드 커서가 선이나 텍스트 버퍼의 끝에 있는 경우 현재 단어 또는 이전 단어 찾습니다. 단어 메서드 이름 중 하나 이면 해당 메서드 이름에 대 한 설명은 요약 정보 내용에 추가 됩니다.  
  
     [!code-vb[VSSDKQuickInfoTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_5.vb)]
     [!code-cs[VSSDKQuickInfoTest#5](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_5.cs)]  
  
8.  Dispose \(\) 메서드를 이후 구현도 해야 <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSource> 구현 <xref:System.IDisposable>:  
  
     [!code-vb[VSSDKQuickInfoTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_6.vb)]
     [!code-cs[VSSDKQuickInfoTest#6](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_6.cs)]  
  
## 요약 정보 원본 공급자 구현  
 공급자는 요약 정보 소스에 MEF 구성 요소 부분으로 자신을 내보낼 및 요약 정보 소스를 인스턴스화하고 데 주로 사용 됩니다. MEF 구성 요소 부분 이기 때문에 다른 MEF 구성 요소 파트를 가져올 수 있습니다.  
  
#### 요약 정보 원본 공급자를 구현 하려면  
  
1.  명명 된 요약 정보 원본 공급자를 선언 `TestQuickInfoSourceProvider` 를 구현 하는 <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSourceProvider>, 및 사용 하 여 내보내기는 <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "소스 요약 정보 도구 설명"는 <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> 의 전에 \= "default", 및 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "text"입니다.  
  
     [!code-vb[VSSDKQuickInfoTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_7.vb)]
     [!code-cs[VSSDKQuickInfoTest#7](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_7.cs)]  
  
2.  두 개의 편집기 서비스를 가져올 <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> 및 <xref:Microsoft.VisualStudio.Text.ITextBufferFactoryService>, 의 속성으로 `TestQuickInfoSourceProvider`합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_8.vb)]
     [!code-cs[VSSDKQuickInfoTest#8](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_8.cs)]  
  
3.  구현 <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSourceProvider.TryCreateQuickInfoSource%2A> 새 반환할 `TestQuickInfoSource`합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_9.vb)]
     [!code-cs[VSSDKQuickInfoTest#9](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_9.cs)]  
  
## 요약 정보 컨트롤러를 구현합니다.  
 요약 정보 컨트롤러 요약 정보를 표시할 시기를 결정 합니다. 이 예제에서는 포인터가 메서드 이름 중 하나에 해당 하는 단어를 위에 있을 때 요약 정보 표시 됩니다. 요약 정보 컨트롤러 요약 정보 세션을 시작 하는 마우스 가리키기 이벤트 처리기를 구현 합니다.  
  
#### 요약 정보 컨트롤러를 구현 하려면  
  
1.  구현 하는 클래스 선언 <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController>, 하 고 이름을 `TestQuickInfoController`합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_10.vb)]
     [!code-cs[VSSDKQuickInfoTest#10](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_10.cs)]  
  
2.  텍스트 보기, 요약 정보 세션 요약 정보 컨트롤러 공급자의 표시 텍스트 버퍼 텍스트 보기에 대 한 private 필드를 추가 합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_11.vb)]
     [!code-cs[VSSDKQuickInfoTest#11](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_11.cs)]  
  
3.  필드를 설정 하 고 마우스 호버 이벤트 처리기를 추가 하는 생성자를 추가 합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_12.vb)]
     [!code-cs[VSSDKQuickInfoTest#12](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_12.cs)]  
  
4.  요약 정보 세션을 시작 하는 마우스 가리키기 이벤트 처리기를 추가 합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_13.vb)]
     [!code-cs[VSSDKQuickInfoTest#13](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_13.cs)]  
  
5.  구현 된 <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController.Detach%2A> 메서드를 컨트롤러 텍스트 보기에서 분리 되 면 마우스 호버 이벤트 처리기를 제거 합니다.  
  
     [!code-vb[VSSDKQuickInfoTest#14](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_14.vb)]
     [!code-cs[VSSDKQuickInfoTest#14](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_14.cs)]  
  
6.  구현 된 <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController.ConnectSubjectBuffer%2A> 메서드 및 <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController.DisconnectSubjectBuffer%2A> 이 예에서는 빈 메서드로 메서드.  
  
     [!code-vb[VSSDKQuickInfoTest#15](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_15.vb)]
     [!code-cs[VSSDKQuickInfoTest#15](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_15.cs)]  
  
## 요약 정보 컨트롤러 공급자 구현  
 요약 정보 컨트롤러의 공급자는 MEF 구성 요소 부분으로 자신을 내보낼 및 요약 정보 컨트롤러를 인스턴스화하고 데 주로 사용 됩니다. MEF 구성 요소 부분 이기 때문에 다른 MEF 구성 요소 파트를 가져올 수 있습니다.  
  
#### 요약 정보 컨트롤러 공급자를 구현 하려면  
  
1.  이라는 클래스를 선언 `TestQuickInfoControllerProvider` 를 구현 하는 <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseControllerProvider>, 및 사용 하 여 내보내기는 <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "도구 설명 요약 정보 컨트롤러"와 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> 으로 "텍스트":  
  
     [!code-vb[VSSDKQuickInfoTest#16](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_16.vb)]
     [!code-cs[VSSDKQuickInfoTest#16](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_16.cs)]  
  
2.  가져오기는 <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoBroker> 속성으로.  
  
     [!code-vb[VSSDKQuickInfoTest#17](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_17.vb)]
     [!code-cs[VSSDKQuickInfoTest#17](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_17.cs)]  
  
3.  구현 된 <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseControllerProvider.TryCreateIntellisenseController%2A> 요약 정보 컨트롤러를 인스턴스화하여 메서드.  
  
     [!code-vb[VSSDKQuickInfoTest#18](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_18.vb)]
     [!code-cs[VSSDKQuickInfoTest#18](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_18.cs)]  
  
## 코드 빌드 및 테스트  
 이 코드를 테스트 하려면 QuickInfoTest 솔루션 빌드하고 실험적 인스턴스에서 실행 합니다.  
  
#### 빌드하고 QuickInfoTest 솔루션을 테스트 하려면  
  
1.  솔루션을 빌드합니다.  
  
2.  디버거에서 이 프로젝트를 실행하면 Visual Studio의 두 번째 인스턴스가 인스턴스화됩니다.  
  
3.  텍스트 파일 형식 단어를 포함 하는 일부 텍스트 "추가" 및 "빼기"를 만듭니다.  
  
4.  "추가"의 각 항목 중 하나 위로 포인터를 이동 합니다. 서명 및 설명이 `add` 메서드를 표시 합니다.  
  
## 참고 항목  
 [연습: 파일 이름 확장명에 콘텐츠 형식 연결](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)