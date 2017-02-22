---
title: "연습: 텍스트 뷰를 사용자 지정 | Microsoft Docs"
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
  - "편집기 [Visual Studio SDK] 새-보기를 사용자 지정"
ms.assetid: 32d32ac8-22ff-4de7-af69-bd46ec4ad9bf
caps.latest.revision: 22
caps.handback.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
---
# 연습: 텍스트 뷰를 사용자 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

해당 편집기 형식 맵에서 다음과 같은 속성을 수정 하 여 텍스트 뷰를 사용자 지정할 수 있습니다.  
  
-   표시기 여백  
  
-   삽입 캐럿  
  
-   캐럿 덮어쓰기  
  
-   선택 된 텍스트  
  
-   선택한 비활성 텍스트 \(즉, 선택한 텍스트에 포커스가 있는\)  
  
-   공백 표시  
  
## 사전 요구 사항  
 이 연습을 수행 하려면 Visual Studio SDK를 설치 해야 합니다. 자세한 내용은 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)을 참조하십시오.  
  
## MEF 프로젝트 만들기  
  
1.  C\# VSIX 프로젝트를 만듭니다. \(에 **새 프로젝트** 대화 상자에서 **Visual C\# \/ 확장성**, 다음 **VSIX 프로젝트**.\) 솔루션의 이름을 `ViewPropertyTest`합니다.  
  
2.  편집기 분류자 항목 템플릿을 프로젝트에 추가 합니다. 자세한 내용은 [편집기 항목 템플릿을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-an-editor-item-template.md)을 참조하세요.  
  
3.  기존 클래스 파일을 삭제 합니다.  
  
## 콘텐츠 형식 정의  
  
1.  클래스 파일을 추가 하 고 이름을 `ViewPropertyModifier`합니다.  
  
2.  다음 코드를 추가 `using` 지시문:  
  
     [!code-cs[VSSDKViewPropertyTest#1](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_1.cs)]
     [!code-vb[VSSDKViewPropertyTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_1.vb)]  
  
3.  이라는 클래스를 선언 `TestViewCreationListener` 에서 상속 되는 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener>합니다. 이 클래스는 다음과 같은 특성을 내보냅니다.  
  
    -   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> 이 수신기가 적용 되는 콘텐츠의 형식을 지정 합니다.  
  
    -   <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute> 이 수신기의 역할을 지정 합니다.  
  
     [!code-cs[VSSDKViewPropertyTest#2](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_2.cs)]
     [!code-vb[VSSDKViewPropertyTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_2.vb)]  
  
4.  이 클래스에서 가져오는 <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMapService>합니다.  
  
     [!code-cs[VSSDKViewPropertyTest#3](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_3.cs)]
     [!code-vb[VSSDKViewPropertyTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_3.vb)]  
  
## 보기 속성 변경  
  
1.  구현 된 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener.TextViewCreated%2A> 메서드 보기 속성 보기를 열 때 변경 됩니다. 변경 하 고을 찾으려면 먼저는 <xref:System.Windows.ResourceDictionary> 찾으려는 보기의 측면에 해당 하는 합니다. 리소스 사전에서 해당 속성을 변경 하 고 속성을 설정 합니다. 에 대 한 호출을 일괄 처리는 <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap.SetProperties%2A> 메서드를 호출 하 여는 <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap.BeginBatchUpdate%2A> 메서드는 속성을 설정 하기 전에 다음의 <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap.EndBatchUpdate%2A> 속성을 설정한 후 합니다.  
  
     [!code-cs[VSSDKViewPropertyTest#4](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_4.cs)]
     [!code-vb[VSSDKViewPropertyTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_4.vb)]  
  
## 빌드 및 코드를 테스트 합니다.  
  
1.  솔루션을 빌드합니다.  
  
     디버거에서이 프로젝트를 실행 하면 Visual Studio의 두 번째 인스턴스가 인스턴스화됩니다.  
  
2.  텍스트 파일을 만들고 일부 텍스트를 입력 합니다.  
  
    -   삽입 캐럿 자홍 고 덮어쓰기 캐럿 옥색 이어야 합니다.  
  
    -   표시기 여백 \(텍스트 뷰 왼쪽\)에 빛 해야 녹색입니다.  
  
3.  방금 입력 한 텍스트를 선택 합니다. 선택한 텍스트의 색 빛 있어야 분홍색 합니다.  
  
4.  텍스트를 선택한 상태에서 텍스트 창 외부 아무 곳 이나 클릭 합니다. 선택한 텍스트의 색을 진한 분홍색 있어야 합니다.  
  
5.  공백 표시를 설정 합니다. \(에 **편집** 메뉴에서 **고급** 클릭 하 고 **공백 보기**\). 일부 탭 텍스트에 입력 합니다. 빨간색 화살표는 탭을 나타내는 표시 되어야 합니다.  
  
## 참고 항목  
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)