---
title: "연습: 텍스트 보기 사용자 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - customizing the view
ms.assetid: 32d32ac8-22ff-4de7-af69-bd46ec4ad9bf
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e890145199fe864d2f7b5010495375bfbc6cc094
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-customizing-the-text-view"></a>연습: 텍스트 보기 사용자 지정
해당 편집기 형식 맵에서 다음과 같은 속성을 수정 하 여 텍스트 보기를 사용자 지정할 수 있습니다.  
  
-   표시기 여백  
  
-   삽입 캐럿  
  
-   캐럿을 덮어쓰기  
  
-   선택한 텍스트  
  
-   선택한 비활성 텍스트 (즉, 선택한 텍스트 포커스를 잃은)  
  
-   공백 표시  
  
## <a name="prerequisites"></a>필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-a-mef-project"></a>MEF 프로젝트 만들기  
  
1.  C# VSIX 프로젝트를 만듭니다. (에 **새 프로젝트** 대화 상자에서 **Visual C# / 확장성**, 다음 **VSIX 프로젝트**.) 솔루션 이름을 `ViewPropertyTest`합니다.  
  
2.  편집기 분류자 항목 템플릿을 프로젝트에 추가 합니다. 자세한 내용은 참조 [편집기 항목 템플릿을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-an-editor-item-template.md)합니다.  
  
3.  기존 클래스 파일을 삭제합니다.  
  
## <a name="defining-the-content-type"></a>콘텐츠 형식 정의  
  
1.  클래스 파일을 추가 하 고 이름을 `ViewPropertyModifier`합니다.  
  
2.  다음 추가 `using` 지시문:  
  
     [!code-csharp[VSSDKViewPropertyTest#1](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_1.cs)]
     [!code-vb[VSSDKViewPropertyTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_1.vb)]  
  
3.  이라는 클래스를 선언 `TestViewCreationListener` 에서 상속 되는 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener>합니다. 이 클래스는 다음과 같은 특성을 내보냅니다.  
  
    -   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>이 수신기가 적용 되는 콘텐츠의 형식을 지정 합니다.  
  
    -   <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute>이 수신기의 역할을 지정 합니다.  
  
     [!code-csharp[VSSDKViewPropertyTest#2](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_2.cs)]
     [!code-vb[VSSDKViewPropertyTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_2.vb)]  
  
4.  이 클래스에서 가져옵니다는 <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMapService>합니다.  
  
     [!code-csharp[VSSDKViewPropertyTest#3](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_3.cs)]
     [!code-vb[VSSDKViewPropertyTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_3.vb)]  
  
## <a name="changing-the-view-properties"></a>보기 속성 변경  
  
1.  구현 된 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener.TextViewCreated%2A> 메서드 보기 속성에서 보기를 열 때 변경 됩니다. 먼저 찾을 변경 하는 <xref:System.Windows.ResourceDictionary> 찾으려는 보기의 측면에 해당 하는 합니다. 리소스 사전에서 적절 한 속성을 변경 하 고 속성을 설정 합니다. 에 대 한 호출을 일괄 처리는 <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap.SetProperties%2A> 메서드를 호출 하 여는 <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap.BeginBatchUpdate%2A> 메서드 속성을 설정 하기 전에 다음의 <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap.EndBatchUpdate%2A> 속성을 설정한 후 합니다.  
  
     [!code-csharp[VSSDKViewPropertyTest#4](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_4.cs)]
     [!code-vb[VSSDKViewPropertyTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_4.vb)]  
  
## <a name="building-and-testing-the-code"></a>코드 빌드 및 테스트  
  
1.  솔루션을 빌드합니다.  
  
     디버거에서 이 프로젝트를 실행하면 Visual Studio의 두 번째 인스턴스가 인스턴스화됩니다.  
  
2.  텍스트 파일을 만들고 일부 텍스트를 입력합니다.  
  
    -   삽입 캐럿 자홍 고 덮어쓰기 캐럿 옥색 이어야 합니다.  
  
    -   표시기 여백 (왼쪽 텍스트 보기)에 밝은 해야 녹색입니다.  
  
3.  방금 입력 한 텍스트를 선택 합니다. 선택한 텍스트의 색 light 있어야 분홍색 합니다.  
  
4.  텍스트를 선택한 상태에서 텍스트 창 외부 아무 곳 이나 클릭 합니다. 선택한 텍스트의 색을 진한 분홍색 있어야 합니다.  
  
5.  공백 표시를 설정 합니다. (에 **편집** 메뉴에서 **고급** 클릭 하 고 **공백 보기**). 일부 탭 텍스트에 입력 합니다. 빨간색 화살표는 탭을 나타내는 메시지가 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)