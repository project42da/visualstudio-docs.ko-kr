---
title: "연습: 서명 도움말 표시 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK]-새 서명 도움말/매개 변수 정보"
ms.assetid: 4a6a884b-5730-4b54-9264-99684f5b523c
caps.latest.revision: 28
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 28
---
# 연습: 서명 도움말 표시
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

서명 도움말 \(라고도 *매개 변수 정보*\)는 매개 변수 목록 시작 문자 \(일반적으로 여는 괄호,\)를 입력 한 사용자는 메서드의 서명 도구 설명에 표시 됩니다. 매개 변수 및 매개 변수 구분 기호 \(쉼표\)를 입력 한 도구 설명에 표시할 굵게 표시 된 다음 매개 변수를 표시 하도록 업데이트 됩니다. 언어 서비스의 컨텍스트에서 시그니처 도움말를 정의할 수 고유의 파일 이름 확장명 및 콘텐츠 형식을 정의 하 고 해당 형식만 대 한 시그니처 도움말을 표시할 수 또는 기존 콘텐츠 형식 \(예: "text"\)에 대 한 시그니처 도움말를 표시할 수 있습니다. 이 연습에서는 "text" 콘텐츠 형식에 대 한 시그니처 도움말을 표시 하는 방법을 보여 줍니다.  
  
 예를 들어, 특정 문자를 입력 하 여 서명 도움말은 일반적으로 트리거됩니다 "\(" \(여는 괄호\), 예를 들어 다른 문자를 입력 하 여 닫히면서 "\)" \(닫는 괄호\). 키 입력에 대 한 명령 처리기를 사용 하 여 문자를 입력 하 여 발생 하는 IntelliSense 기능을 구현할 수 있습니다 \(의 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스\) 및 구현 하는 처리기 공급자는 <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> 인터페이스입니다. 서명을 시그니처 도움말에 참여 하는 목록, 시그니처 도움말 소스를 만들려면 구현에서 <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSource> 인터페이스와 구현 하는 원본 공급자는 <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSourceProvider> 인터페이스입니다. 공급자는 프레임 워크 MEF \(Managed Extensibility\) 구성 요소 부분으로 설정 되며 서비스 및 브로커, 예를 들어, 소스 및 컨트롤러 클래스를 내보내기 및 가져오기에 대 한 책임은 <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>, 텍스트 버퍼에서 탐색할 수 있는 및 <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpBroker>, 시그니처 도움말 세션의 트리거.  
  
 이 연습에서는 하드 코드 된 일련의 식별자에 대 한 시그니처 도움말을 구현 하는 방법을 보여 줍니다. 전체 구현에서는 언어는 해당 콘텐츠를 제공 하는 일을 담당 합니다.  
  
## 사전 요구 사항  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하세요.  
  
## MEF 프로젝트 만들기  
  
#### MEF 프로젝트를 만들려면  
  
1.  C\# VSIX 프로젝트를 만듭니다. \(에 **새 프로젝트** 대화 상자에서 **Visual C\# \/ 확장성**, 다음 **VSIX 프로젝트**.\) 솔루션의 이름을 `SignatureHelpTest`합니다.  
  
2.  편집기 분류자 항목 템플릿을 프로젝트에 추가 합니다. 자세한 내용은 [편집기 항목 템플릿을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-an-editor-item-template.md)을 참조하세요.  
  
3.  기존 클래스 파일을 삭제합니다.  
  
4.  프로젝트에 다음 참조를 추가 하 고 있는지 **{2\>copylocal** 로 설정 된 `false`:  
  
     Microsoft.VisualStudio.Editor  
  
     Microsoft.VisualStudio.Language.Intellisense  
  
     Microsoft.VisualStudio.OLE.Interop  
  
     Microsoft.VisualStudio.Shell.14.0  
  
     Microsoft.VisualStudio.TextManager.Interop  
  
## 서명 구현 서명 및 매개 변수 도움말  
 시그니처 도움말 소스를 구현 하는 서명을 기반 <xref:Microsoft.VisualStudio.Language.Intellisense.ISignature>, 를 구현 하는 매개 변수가 포함 된 각 <xref:Microsoft.VisualStudio.Language.Intellisense.IParameter>합니다. 완전 한 구현에서 해당 언어 설명서에서이 정보를 가져올 수는 있지만이 예제에서는 시그니처는 하드 코드 된.  
  
#### 서명 시그니처 도움말 및 매개 변수를 구현 하려면  
  
1.  클래스 파일을 추가 하 고 이름을 `SignatureHelpSource`합니다.  
  
2.  다음 import를 추가 합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_1.vb)]
     [!code-cs[VSSDKSignatureHelpTest#1](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_1.cs)]  
  
3.  라는 클래스를 추가 `TestParameter` 를 구현 하는 <xref:Microsoft.VisualStudio.Language.Intellisense.IParameter>합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_2.vb)]
     [!code-cs[VSSDKSignatureHelpTest#2](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_2.cs)]  
  
4.  모든 속성을 설정 하는 생성자를 추가 합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_3.vb)]
     [!code-cs[VSSDKSignatureHelpTest#3](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_3.cs)]  
  
5.  속성을 추가 <xref:Microsoft.VisualStudio.Language.Intellisense.IParameter>합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_4.vb)]
     [!code-cs[VSSDKSignatureHelpTest#4](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_4.cs)]  
  
6.  라는 클래스를 추가 `TestSignature` 를 구현 하는 <xref:Microsoft.VisualStudio.Language.Intellisense.ISignature>합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_5.vb)]
     [!code-cs[VSSDKSignatureHelpTest#5](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_5.cs)]  
  
7.  일부 개인 필드를 추가 합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_6.vb)]
     [!code-cs[VSSDKSignatureHelpTest#6](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_6.cs)]  
  
8.  필드를 설정 하 고 구독 하는 생성자를 추가 <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> 이벤트입니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_7.vb)]
     [!code-cs[VSSDKSignatureHelpTest#7](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_7.cs)]  
  
9. 선언 된 `CurrentParameterChanged` 이벤트입니다. 이 이벤트는 서명에서 매개 변수 중 하나에서 사용자가 입력할 때 발생 합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_8.vb)]
     [!code-cs[VSSDKSignatureHelpTest#8](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_8.cs)]  
  
10. 구현은 <xref:Microsoft.VisualStudio.Language.Intellisense.ISignature.CurrentParameter%2A> 한다는 발생 하므로 속성은 `CurrentParameterChanged` 이벤트 속성 값이 변경 됩니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_9.vb)]
     [!code-cs[VSSDKSignatureHelpTest#9](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_9.cs)]  
  
11. 발생 시키는 메서드를 추가 하는 `CurrentParameterChanged` 이벤트입니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_10.vb)]
     [!code-cs[VSSDKSignatureHelpTest#10](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_10.cs)]  
  
12. 쉼표의 수를 비교 하 여 현재 매개 변수를 계산 하는 메서드를 추가 하는 <xref:Microsoft.VisualStudio.Language.Intellisense.ISignature.ApplicableToSpan%2A> 서명에 쉼표의 수입니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_11.vb)]
     [!code-cs[VSSDKSignatureHelpTest#11](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_11.cs)]  
  
13. 에 대 한 이벤트 처리기를 추가 <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> 이벤트를 호출 하 여 `ComputeCurrentParameter()` 메서드.  
  
     [!code-vb[VSSDKSignatureHelpTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_12.vb)]
     [!code-cs[VSSDKSignatureHelpTest#12](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_12.cs)]  
  
14. <xref:Microsoft.VisualStudio.Language.Intellisense.ISignature.ApplicableToSpan%2A> 속성을 구현합니다. 이 속성에 저장 된 <xref:Microsoft.VisualStudio.Text.ITrackingSpan> 서명을 적용 되는 버퍼의 텍스트 범위에 해당 하는 합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_13.vb)]
     [!code-cs[VSSDKSignatureHelpTest#13](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_13.cs)]  
  
15. 다른 매개 변수를 구현 합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#14](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_14.vb)]
     [!code-cs[VSSDKSignatureHelpTest#14](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_14.cs)]  
  
## 서명 도움말 소스 구현  
 시그니처 도움말 원본은 서명 정보를 제공 하기 위한 집합입니다.  
  
#### 시그니처 도움말 소스를 구현 하려면  
  
1.  라는 클래스를 추가 `TestSignatureHelpSource` 를 구현 하는 <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSource>합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#15](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_15.vb)]
     [!code-cs[VSSDKSignatureHelpTest#15](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_15.cs)]  
  
2.  텍스트 버퍼에 대 한 참조를 추가 합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#16](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_16.vb)]
     [!code-cs[VSSDKSignatureHelpTest#16](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_16.cs)]  
  
3.  텍스트 버퍼와 시그니처 도움말 소스 공급자를 설정 하는 생성자를 추가 합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#17](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_17.vb)]
     [!code-cs[VSSDKSignatureHelpTest#17](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_17.cs)]  
  
4.  <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSource.AugmentSignatureHelpSession%2A> 메서드를 구현합니다. 이 예제에서는 시그니처는 하드 코드 하지만 완전 한 구현에서 해당 언어 설명서에서이 정보를 받을 것입니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#18](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_18.vb)]
     [!code-cs[VSSDKSignatureHelpTest#18](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_18.cs)]  
  
5.  도우미 메서드는 `CreateSignature()` 단지 설명을 위해서만 제공 됩니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#19](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_19.vb)]
     [!code-cs[VSSDKSignatureHelpTest#19](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_19.cs)]  
  
6.  <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSource.GetBestMatch%2A> 메서드를 구현합니다. 이 예제에서는 두 가지 서명, 각각에 두 개의 매개 변수가 있습니다. 따라서이 메서드는 필요 하지 않습니다. 둘 이상의 시그니처 도움말 소스를, 사용할 수 있는 완전 한 구현에서이 메서드는 우선 순위가 가장 높은 시그니처 도움말 소스 일치 하는 시그니처를 제공할 수 있는지 여부를 결정에 사용 됩니다. 그렇지 않을 경우 메서드가 null을 반환 하 고\-우선 순위가 가장 높은 소스는 일치 하는 항목을 제공 하 라는 메시지가 표시 됩니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#20](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_20.vb)]
     [!code-cs[VSSDKSignatureHelpTest#20](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_20.cs)]  
  
7.  Dispose \(\) 메서드를 구현 합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#21](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_21.vb)]
     [!code-cs[VSSDKSignatureHelpTest#21](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_21.cs)]  
  
## 서명 도움말 원본 공급자를 구현합니다.  
 시그니처 도움말 소스 공급자는 프레임 워크 MEF \(Managed Extensibility\) 구성 요소 부분 내보내기에 대 한 시그니처 도움말 소스를 인스턴스화하기 위한 담당 합니다.  
  
#### 시그니처 도움말 원본 공급자를 구현 하려면  
  
1.  라는 클래스를 추가 `TestSignatureHelpSourceProvider` 를 구현 하는 <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSourceProvider>, 및 사용 하 여 내보내기는 <xref:Microsoft.VisualStudio.Utilities.NameAttribute>,  <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> 으로 "텍스트" 및 <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> 의 전에 \= "default"입니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#22](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_22.vb)]
     [!code-cs[VSSDKSignatureHelpTest#22](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_22.cs)]  
  
2.  구현 <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSourceProvider.TryCreateSignatureHelpSource%2A> 인스턴스화하여는 `TestSignatureHelpSource`합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#23](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_23.vb)]
     [!code-cs[VSSDKSignatureHelpTest#23](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_23.cs)]  
  
## 명령 처리기를 구현합니다.  
 서명 도움말에 의해 트리거되면 일반적으로 \(문자와으로 해제 됨는\) 문자입니다. 구현 하 여 이러한 키 입력을 처리할 수 있습니다는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 을 받았을 때 시그니처 도움말 세션은 \(문자 앞에 알려진된 메서드 이름 및 받았을 때 세션을 해제 한\) 문자.  
  
#### 명령 처리기를 구현 하려면  
  
1.  라는 클래스를 추가 `TestSignatureHelpCommand` 를 구현 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#24](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_24.vb)]
     [!code-cs[VSSDKSignatureHelpTest#24](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_24.cs)]  
  
2.  Private 필드에 대 한 추가 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 어댑터 \(체인의 명령 처리기를 명령 처리기를 추가할 수 있습니다\), 텍스트 보기, 시그니처 도움말 브로커 및 세션에는 <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigator>, 처리와 다음 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#25](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_25.vb)]
     [!code-cs[VSSDKSignatureHelpTest#25](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_25.cs)]  
  
3.  이러한 필드를 초기화 하 고 명령 필터 체인의 명령 필터를 추가 하는 생성자를 추가 합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#26](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_26.vb)]
     [!code-cs[VSSDKSignatureHelpTest#26](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_26.cs)]  
  
4.  구현에서 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> 명령 필터를 받으면 시그니처 도움말 세션을 트리거하는 메서드는 \(알려진된 메서드 이름 및를 받을 때 세션을 해제 한 후 문자는\) 세션이 여전히 활성 상태인 동안 문자. 모든 경우에 명령이 전달 됩니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#27](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_27.vb)]
     [!code-cs[VSSDKSignatureHelpTest#27](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_27.cs)]  
  
5.  구현 된 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드를 항상 명령을 전달 합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#28](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_28.vb)]
     [!code-cs[VSSDKSignatureHelpTest#28](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_28.cs)]  
  
## 서명 도움말 명령 공급자를 구현합니다.  
 구현 하 여 서명 도움말 명령을 제공할 수 있습니다는 <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> 텍스트 뷰를 만들 때 명령 처리기를 인스턴스화할 수 있습니다.  
  
#### 시그니처 도움말 명령 공급자를 구현 하려면  
  
1.  라는 클래스를 추가 `TestSignatureHelpController` 를 구현 하는 <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> 및 사용 하 여 내보내기는 <xref:Microsoft.VisualStudio.Utilities.NameAttribute>, <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>, 및 <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute>합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#29](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_29.vb)]
     [!code-cs[VSSDKSignatureHelpTest#29](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_29.cs)]  
  
2.  가져오기는 <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService> \(가져오는 데는 <xref:Microsoft.VisualStudio.Text.Editor.ITextView>, 주어진는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 개체\), <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> \(현재 단어를 찾는 사용\), 및 <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpBroker> \(시그니처 도움말 세션 트리거\)를 합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#30](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_30.vb)]
     [!code-cs[VSSDKSignatureHelpTest#30](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_30.cs)]  
  
3.  구현 된 <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener.VsTextViewCreated%2A> 인스턴스화하여 메서드는 `TestSignatureCommandHandler`합니다.  
  
     [!code-vb[VSSDKSignatureHelpTest#31](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_31.vb)]
     [!code-cs[VSSDKSignatureHelpTest#31](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_31.cs)]  
  
## 코드 빌드 및 테스트  
 이 코드를 테스트 하려면 SignatureHelpTest 솔루션 빌드하고 실험적 인스턴스에서 실행 합니다.  
  
#### 빌드하고 SignatureHelpTest 솔루션을 테스트 하려면  
  
1.  솔루션을 빌드합니다.  
  
2.  디버거에서 이 프로젝트를 실행하면 Visual Studio의 두 번째 인스턴스가 인스턴스화됩니다.  
  
3.  텍스트 파일 형식 "추가" 라는 단어를 포함 하는 일부 텍스트와 여는 괄호를 만듭니다.  
  
4.  여는 괄호를 입력 한 후에 대 한 두 개의 서명의 목록을 표시 하는 도구 설명이 표시 됩니다는 `add()` 메서드.  
  
## 참고 항목  
 [연습: 파일 이름 확장명에 콘텐츠 형식 연결](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)