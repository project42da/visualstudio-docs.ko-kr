---
title: "연습: 문 완성 표시 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 새-문 완성"
ms.assetid: f3152c4e-7673-4047-a079-2326941d1c83
caps.latest.revision: 36
caps.handback.revision: 36
ms.author: "gregvanl"
manager: "ghogen"
---
# 연습: 문 완성 표시
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

완성 기능을 제공 하려는 식별자를 정의 하 고 다음 완성 세션을 트리거하지 기반 언어 문 완성을 구현할 수 있습니다. 언어 서비스의 컨텍스트에서 문 완성을 정의 하, 고유한 파일 이름 확장명 및 콘텐츠 형식을 정의 하 고 다음 해당 형식만 대 한 완료를 표시할 수 하거나 기존 콘텐츠 형식에 대 한 완료를 트리거할 수 있습니다\-예를 들어 "일반"입니다. 이 연습에서는 텍스트 파일의 콘텐츠 형식인 "일반 텍스트" 콘텐츠 형식에 대 한 문 완성을 트리거하는 방법을 보여 줍니다. "Text" 콘텐츠 유형 코드 및 XML 파일을 비롯 한 모든 콘텐츠 형식의 상위 항목입니다.  
  
 문 완성은 일반적으로 특정 문자를 입력 하 여 트리거됩니다\-"를 사용 하 여" 등의 식별자의 시작 부분을 입력 하 여 예를 들어 있습니다. 선택 영역을 커밋하지 스페이스바, 탭 또는 Enter 키를 눌러 일반적으로 해제 됩니다. 키 입력에 대 한 명령 처리기를 사용 하 여 문자를 입력 하 여 발생 하는 IntelliSense 기능을 구현할 수 있습니다 \(의 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스\) 및 구현 하는 처리기 공급자는 <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> 인터페이스입니다. 완료에 참여 하는 식별자의 목록을 완성 소스를 만들려면 구현는 <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource> 인터페이스와 완료 원본 공급자 \(의 <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSourceProvider> 인터페이스\)입니다. 공급자는 프레임 워크 MEF \(Managed Extensibility\) 구성 요소입니다. 서비스 및 브로커 소스 및 컨트롤러 클래스를 내보내기 및 가져오기 작업을 담당 하는\-예를 들어는 <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>, 탐색 텍스트 버퍼의 수 및 <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionBroker>, 완성 세션의 트리거.  
  
 이 연습에서는 하드 코드 된 일련의 식별자에 대 한 문 완성을 구현 하는 방법을 보여 줍니다. 전체 구현에서 언어 서비스와 해당 언어 설명서는 해당 콘텐츠를 제공 합니다.  
  
## 사전 요구 사항  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하세요.  
  
## MEF 프로젝트 만들기  
  
#### MEF 프로젝트를 만들려면  
  
1.  C\# VSIX 프로젝트를 만듭니다. \(에 **새 프로젝트** 대화 상자에서 **Visual C\# \/ 확장성**, 다음 **VSIX 프로젝트**.\) 솔루션의 이름을 `CompletionTest`합니다.  
  
2.  편집기 분류자 항목 템플릿을 프로젝트에 추가 합니다. 자세한 내용은 [편집기 항목 템플릿을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-an-editor-item-template.md)을 참조하십시오.  
  
3.  기존 클래스 파일을 삭제합니다.  
  
4.  프로젝트에 다음 참조를 추가 하 고 있는지 확인 **{2\>copylocal** 로 설정 된 `false`:  
  
     Microsoft.VisualStudio.Editor  
  
     Microsoft.VisualStudio.Language.Intellisense  
  
     Microsoft.VisualStudio.OLE.Interop  
  
     Microsoft.VisualStudio.Shell.14.0  
  
     Microsoft.VisualStudio.Shell.Immutable.10.0  
  
     Microsoft.VisualStudio.TextManager.Interop  
  
## 완료 소스 구현  
 완료 소스는 식별자의 집합을 수집 하 고 사용자는 완료 트리거 같은 식별자의 첫 번째 문자를 입력할 때 완료 창에 콘텐츠를 추가 하는 일을 담당 합니다. 이 예제에서는 식별자 및 해당 설명을 보려면은에 하드 코드 된 <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource.AugmentCompletionSession%2A> 메서드. 대부분의 실제 사용 완성 목록을 채우기 위해 토큰을 가져오는 해당 언어의 파서를 사용 합니다.  
  
#### 완료 소스를 구현 하려면  
  
1.  클래스 파일을 추가 하 고 이름을 `TestCompletionSource`합니다.  
  
2.  이러한 가져오기를 추가 합니다.  
  
     [!code-cs[VSSDKCompletionTest#1](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_1.cs)]
     [!code-vb[VSSDKCompletionTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_1.vb)]  
  
3.  에 대 한 클래스 선언을 수정 `TestCompletionSource` 구현 되도록 <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource>:  
  
     [!code-cs[VSSDKCompletionTest#2](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_2.cs)]
     [!code-vb[VSSDKCompletionTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_2.vb)]  
  
4.  Private 필드의 목록과 원본 공급자, 텍스트 버퍼에 대 한 추가 <xref:Microsoft.VisualStudio.Language.Intellisense.Completion> \(하는 개체는 완성 세션에 참여 하는 식별자에 해당\):  
  
     [!code-cs[VSSDKCompletionTest#3](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_3.cs)]
     [!code-vb[VSSDKCompletionTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_3.vb)]  
  
5.  원본 공급자 및 버퍼를 설정 하는 생성자를 추가 합니다.`TestCompletionSourceProvider` 클래스는 이후 단계에서 정의 됩니다.  
  
     [!code-cs[VSSDKCompletionTest#4](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_4.cs)]
     [!code-vb[VSSDKCompletionTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_4.vb)]  
  
6.  구현 된 <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource.AugmentCompletionSession%2A> 컨텍스트에서 제공 하려는 완료를 포함 하는 완료 집합을 추가 하 여 메서드. 집합을 포함 하는 각 완성 집합 <xref:Microsoft.VisualStudio.Language.Intellisense.Completion> 완료 완료 창의 탭에 해당 합니다. \(Visual Basic 프로젝트에서 완료 창의 탭 이름은 **일반적인** 및 **모든**.\) FindTokenSpanAtPosition 메서드는 다음 단계에서 정의 됩니다.  
  
     [!code-cs[VSSDKCompletionTest#5](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_5.cs)]
     [!code-vb[VSSDKCompletionTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_5.vb)]  
  
7.  다음 메서드는 커서의 위치에서 현재 단어를 찾는 데 사용 됩니다.  
  
     [!code-cs[VSSDKCompletionTest#6](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_6.cs)]
     [!code-vb[VSSDKCompletionTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_6.vb)]  
  
8.  구현 된 `Dispose()` 메서드:  
  
     [!code-cs[VSSDKCompletionTest#7](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_7.cs)]
     [!code-vb[VSSDKCompletionTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_7.vb)]  
  
## 완료 원본 공급자를 구현합니다.  
 완료 원본 공급자에는 완료 소스를 인스턴스화하는 MEF 구성 요소 부분입니다.  
  
#### 완료 원본 공급자를 구현 하려면  
  
1.  라는 클래스를 추가 `TestCompletionSourceProvider` 를 구현 하는 <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSourceProvider>합니다. 이 클래스와 내보내기는 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "일반"텍스트의 및 <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "테스트 완료"의입니다.  
  
     [!code-cs[VSSDKCompletionTest#8](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_8.cs)]
     [!code-vb[VSSDKCompletionTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_8.vb)]  
  
2.  가져오기는 <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>, 는 완료 소스에서 현재 단어를 찾는 데 사용 됩니다.  
  
     [!code-cs[VSSDKCompletionTest#9](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_9.cs)]
     [!code-vb[VSSDKCompletionTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_9.vb)]  
  
3.  구현 된 <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSourceProvider.TryCreateCompletionSource%2A> 완료 소스를 인스턴스화하기 위한 메서드를 합니다.  
  
     [!code-cs[VSSDKCompletionTest#10](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_10.cs)]
     [!code-vb[VSSDKCompletionTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_10.vb)]  
  
## 완료 명령 처리기 공급자 구현  
 완료 명령 처리기 공급자에서 파생 되는 <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener>, 텍스트 뷰 생성 이벤트를 수신 하 고 변환에서 뷰는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>\-Visual Studio shell의 명령 체인에 명령 추가 수 있게 해줍니다\-에 <xref:Microsoft.VisualStudio.Text.Editor.ITextView>. 이 클래스는 MEF 내보내기 이기 때문에 자체 명령 처리기에 필요한 서비스를 가져오는 사용할 수 있습니다.  
  
#### 완료 명령 처리기 공급자를 구현 하려면  
  
1.  라는 파일을 추가 `TestCompletionCommandHandler`합니다.  
  
2.  다음 using 문을 추가 합니다.  
  
     [!code-cs[VSSDKCompletionTest#11](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_11.cs)]
     [!code-vb[VSSDKCompletionTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_11.vb)]  
  
3.  라는 클래스를 추가 `TestCompletionHandlerProvider` 를 구현 하는 <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener>합니다. 내보내기 사용 하 여이 클래스는 <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "토큰 완료 처리기"의 한 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "일반 텍스트"의 및 <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute> 의 <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Editable>합니다.  
  
     [!code-cs[VSSDKCompletionTest#12](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_12.cs)]
     [!code-vb[VSSDKCompletionTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_12.vb)]  
  
4.  가져오기는 <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService>, 변환할 수 있는 한 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 에 <xref:Microsoft.VisualStudio.Text.Editor.ITextView>,  <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionBroker>, 및 <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> 표준 Visual Studio 서비스에 액세스할 수 있도록 하는 합니다.  
  
     [!code-cs[VSSDKCompletionTest#13](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_13.cs)]
     [!code-vb[VSSDKCompletionTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_13.vb)]  
  
5.  구현 된 <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener.VsTextViewCreated%2A> 메서드 명령 처리기를 인스턴스화합니다.  
  
     [!code-cs[VSSDKCompletionTest#14](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_14.cs)]
     [!code-vb[VSSDKCompletionTest#14](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_14.vb)]  
  
## 완료 명령 처리기를 구현합니다.  
 구현 해야 하므로 문 완성 키 입력에 의해 트리거될는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 받고 트리거, 커밋 및 완료 세션을 해제 하는 키 입력을 처리 하는 인터페이스입니다.  
  
#### 완료 명령 처리기를 구현 하려면  
  
1.  라는 클래스를 추가 `TestCompletionCommandHandler` 를 구현 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>:  
  
     [!code-cs[VSSDKCompletionTest#15](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_15.cs)]
     [!code-vb[VSSDKCompletionTest#15](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_15.vb)]  
  
2.  다음 명령 처리기 \(전달 하는 명령\), 텍스트 뷰 \(다양 한 서비스에 액세스할 수 있도록\)이 표시 하는 명령 처리기 공급자에 대 한 private 필드 추가 및 완료 세션:  
  
     [!code-cs[VSSDKCompletionTest#16](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_16.cs)]
     [!code-vb[VSSDKCompletionTest#16](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_16.vb)]  
  
3.  텍스트 뷰 및 공급자 필드를 설정 하 고 명령 체인에 명령을 추가 하는 생성자를 추가 합니다.  
  
     [!code-cs[VSSDKCompletionTest#17](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_17.cs)]
     [!code-vb[VSSDKCompletionTest#17](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_17.vb)]  
  
4.  구현 된 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 따라 명령을 전달 하 여 메서드:  
  
     [!code-cs[VSSDKCompletionTest#18](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_18.cs)]
     [!code-vb[VSSDKCompletionTest#18](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_18.vb)]  
  
5.  <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> 메서드를 구현합니다. 이 메서드는 키 입력을 받으면 이러한 작업 중 하나를 수행 해야 합니다.  
  
    -   버퍼에 기록 하 고 다음 트리거 또는 완료 필터링 문자를 허용 합니다. \(인쇄 문자가 작업을 수행 합니다.\)  
  
    -   커밋의 완료 하지만 문자 버퍼에 쓸 수를 허용 하지 마십시오. \(공백, 탭 및 Enter 경우 이렇게 완성 세션이 표시 됩니다.\)  
  
    -   명령 다음 처리기를 전달 하도록 허용 합니다. \(모든 다른 명령입니다.\)  
  
     이 메서드가 UI를 표시할 수 있으므로 호출 <xref:Microsoft.VisualStudio.Shell.VsShellUtilities.IsInAutomationFunction%2A> 자동화 컨텍스트에서 호출 되지 않도록 해야 합니다.  
  
     [!code-cs[VSSDKCompletionTest#19](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_19.cs)]
     [!code-vb[VSSDKCompletionTest#19](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_19.vb)]  
  
6.  이 코드는 완료 세션을 시작 하는 전용 메서드.  
  
     [!code-cs[VSSDKCompletionTest#20](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_20.cs)]
     [!code-vb[VSSDKCompletionTest#20](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_20.vb)]  
  
7.  다음 예제는 이전에서 등록을 취소 하는 개인 메서드는 <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseSession.Dismissed> 이벤트:  
  
     [!code-cs[VSSDKCompletionTest#21](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_21.cs)]
     [!code-vb[VSSDKCompletionTest#21](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_21.vb)]  
  
## 코드 빌드 및 테스트  
 이 코드를 테스트 하려면 CompletionTest 솔루션 빌드하고 실험적 인스턴스에서 실행 합니다.  
  
#### 빌드하고 CompletionTest 솔루션을 테스트 하려면  
  
1.  솔루션을 빌드합니다.  
  
2.  디버거에서 이 프로젝트를 실행하면 Visual Studio의 두 번째 인스턴스가 인스턴스화됩니다.  
  
3.  텍스트 파일을 만들고 "추가" 라는 단어가 포함 된 일부 텍스트를 입력 합니다.  
  
4.  입력할 때 먼저 "a"와 "d" 다음 "addition" 및 "조정" 포함 된 목록이 표시 됩니다. 또한 선택 되어 있는지 확인 합니다. 다른 "d"를 입력 하면 목록에만 "추가"를 현재 선택한 있어야 합니다. "Addition" 스페이스바, 탭 또는 Enter 키를 눌러 커밋하거나 Esc 또는 다른 키를 입력 하 여 목록을 해제 수 있습니다.  
  
## 참고 항목  
 [연습: 파일 이름 확장명에 콘텐츠 형식 연결](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)