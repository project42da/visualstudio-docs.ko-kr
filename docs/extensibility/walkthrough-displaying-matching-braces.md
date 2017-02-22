---
title: "연습: 일치 하는 중괄호를 표시합니다. | Microsoft Docs"
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
  - "편집기 [Visual Studio SDK] 새-중괄호 일치"
ms.assetid: 5af08ac7-1d08-4ccf-997e-01aa6cb3d3d7
caps.latest.revision: 27
caps.handback.revision: 27
ms.author: "gregvanl"
manager: "ghogen"
---
# 연습: 일치 하는 중괄호를 표시합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

중괄호 일치, 일치 시킬 중괄호를 정의 하 고 텍스트 표식 태그 캐럿 중괄호 중 하나에 있을 때에 여는 중괄호를 추가 하 여 같은 기반 언어 기능을 구현할 수 있습니다. 언어의 컨텍스트에서 중괄호를 정의할 수 또는 고유한 파일 이름 확장명 및 콘텐츠 형식을 정의 하 고 해당 형식만 태그를 적용할 수 또는 기존 콘텐츠 형식 \(예: "text"\)에 태그를 적용할 수 있습니다. 다음 연습에서는 중괄호 일치 하는 "text" 콘텐츠 형식에 대 한 태그를 적용 하는 방법을 보여 줍니다.  
  
## 사전 요구 사항  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하세요.  
  
## MEF\(Managed Extensibility Framework\) 프로젝트 만들기  
  
#### MEF 프로젝트를 만들려면  
  
1.  편집기 분류자 프로젝트를 만듭니다. 솔루션의 이름을 `BraceMatchingTest`합니다.  
  
2.  편집기 분류자 항목 템플릿을 프로젝트에 추가 합니다. 자세한 내용은 [편집기 항목 템플릿을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-an-editor-item-template.md)을 참조하세요.  
  
3.  기존 클래스 파일을 삭제합니다.  
  
## 태거 일치 하는 중괄호를 구현 합니다.  
 Visual Studio에서 사용 되는 것을 비슷한 효과 강조 표시 하는 중괄호를 가져오려면 형식의 태거를 구현할 수 있습니다 <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>합니다. 다음 코드에는 중첩의 모든 수준에서 중괄호 쌍에 대 한 태거를 정의 하는 방법을 보여 줍니다. 이 예제에서는 중괄호 쌍. {} 태거 생성자에 정의 되어 있으며 전체 언어 구현 언어 사양에는 관련 중괄호 쌍 정의 됩니다.  
  
#### 태거 일치 하는 중괄호를 구현 하려면  
  
1.  클래스 파일을 추가 하 고 중괄호 일치 라는 이름을 지정 합니다.  
  
2.  다음 네임 스페이스를 가져옵니다.  
  
     [!code-cs[VSSDKBraceMatchingTest#1](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_1.cs)]
     [!code-vb[VSSDKBraceMatchingTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_1.vb)]  
  
3.  클래스 정의 `BraceMatchingTagger` 에서 상속 되는 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> 형식의 <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>합니다.  
  
     [!code-cs[VSSDKBraceMatchingTest#2](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_2.cs)]
     [!code-vb[VSSDKBraceMatchingTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_2.vb)]  
  
4.  텍스트 보기, 소스 버퍼 및 현재 스냅숏 지점 및 또한 중괄호 쌍의 집합에 대 한 속성을 추가 합니다.  
  
     [!code-cs[VSSDKBraceMatchingTest#3](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_3.cs)]
     [!code-vb[VSSDKBraceMatchingTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_3.vb)]  
  
5.  태거 생성자에서 속성을 설정 하 고 변경 이벤트 보기에 가입 <xref:Microsoft.VisualStudio.Text.Editor.ITextCaret.PositionChanged> 및 <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged>합니다. 이 예제에서는 설명을 위해 일치 하는 쌍도 정의 됩니다 생성자에서.  
  
     [!code-cs[VSSDKBraceMatchingTest#4](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_4.cs)]
     [!code-vb[VSSDKBraceMatchingTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_4.vb)]  
  
6.  일부로 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> 구현 TagsChanged 이벤트를 선언 합니다.  
  
     [!code-cs[VSSDKBraceMatchingTest#5](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_5.cs)]
     [!code-vb[VSSDKBraceMatchingTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_5.vb)]  
  
7.  현재 캐럿 위치를 업데이트 하는 이벤트 처리기는 `CurrentChar` 속성과 TagsChanged 이벤트 발생 합니다.  
  
     [!code-cs[VSSDKBraceMatchingTest#6](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_6.cs)]
     [!code-vb[VSSDKBraceMatchingTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_6.vb)]  
  
8.  구현 된 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> 현재 문자가 않은 중괄호 또는 때 이전 문자는 Visual Studio에서와 같이 닫는 중괄호와 일치 하도록 메서드의 중괄호 중 하나입니다. 일치 항목이 발견 되 면이 메서드는 여는 중괄호 및 닫는 중괄호에 대 한 두 개의 태그를 인스턴스화합니다.  
  
     [!code-cs[VSSDKBraceMatchingTest#7](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_7.cs)]
     [!code-vb[VSSDKBraceMatchingTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_7.vb)]  
  
9. 다음 private 메서드는 중첩의 모든 수준에서 일치 하는 중괄호를 찾습니다. 첫 번째 방법은 열기 문자와 일치 하는 닫기 문자를 찾습니다.  
  
     [!code-cs[VSSDKBraceMatchingTest#8](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_8.cs)]
     [!code-vb[VSSDKBraceMatchingTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_8.vb)]  
  
10. 다음 도우미 메서드는 열려 있는 닫기 문자와 일치 하는 문자를 찾습니다.  
  
     [!code-cs[VSSDKBraceMatchingTest#9](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_9.cs)]
     [!code-vb[VSSDKBraceMatchingTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_9.vb)]  
  
## 중괄호 일치 태거 공급자 구현  
 한 태거를 구현 하는 것 외에도 구현 하 고 내보내기 태거 공급자도 해야 합니다. 이 경우 공급자의 content\-type은 "text"입니다. 즉, 모든 형식의 텍스트 파일에 표시 됩니다 중괄호 일치 있지만 보다 자세한 구현 중괄호 일치를 특정 콘텐츠 형식에만 적용 됩니다.  
  
#### 중괄호 일치 하는 태거 공급자를 구현 하려면  
  
1.  상속 되는 태거 공급자를 선언 <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider>, BraceMatchingTaggerProvider, 이름을 하 고 사용 하 여 내보내기는 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> 으로 "텍스트" 및 <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> 의 <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>합니다.  
  
     [!code-cs[VSSDKBraceMatchingTest#10](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_10.cs)]
     [!code-vb[VSSDKBraceMatchingTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_10.vb)]  
  
2.  구현 된 <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider.CreateTagger%2A> 를 인스턴스화하는 BraceMatchingTagger 메서드.  
  
     [!code-cs[VSSDKBraceMatchingTest#11](../extensibility/codesnippet/CSharp/walkthrough-displaying-matching-braces_11.cs)]
     [!code-vb[VSSDKBraceMatchingTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-matching-braces_11.vb)]  
  
## 코드 빌드 및 테스트  
 이 코드를 테스트 하려면 BraceMatchingTest 솔루션 빌드하고 실험적 인스턴스에서 실행 합니다.  
  
#### 빌드하고 BraceMatchingTest 솔루션을 테스트 하려면  
  
1.  솔루션을 빌드합니다.  
  
2.  디버거에서 이 프로젝트를 실행하면 Visual Studio의 두 번째 인스턴스가 인스턴스화됩니다.  
  
3.  텍스트 파일을 만들고는 중괄호를 포함 하는 일부 텍스트를 입력 합니다.  
  
    ```  
    hello {  
    goodbye}  
  
    {}  
  
    {hello}  
    ```  
  
4.  전에 중괄호에 캐럿을 배치할 때 해당 중괄호와 일치 하는 닫는 중괄호 강조 표시 됩니다. 바로 닫는 중괄호 뒤 커서를 놓으면 해당 중괄호와 일치 하는 여는 중괄호 강조 표시 됩니다.  
  
## 참고 항목  
 [연습: 파일 이름 확장명에 콘텐츠 형식 연결](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)