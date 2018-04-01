---
title: '연습: 개요 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], new - outlining
ms.assetid: d75a44aa-265a-44d4-9c28-457f59c4ff9f
caps.latest.revision: 30
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 15dd5f0121fca86a38631bf775ec25d4428632e1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-outlining"></a>연습: 개요
개요 확장 또는 축소 하려면 텍스트 영역의 종류를 정의 하 여 같은 언어 기반 기능을 구현할 수 있습니다. 언어 서비스의 컨텍스트에서 영역을 정의할 수 있습니다 또는 고유한 파일 이름 확장명 및 콘텐츠 형식을 정의 하 고 영역 정의 해당 형식에만 적용할 수 있습니다 또는 기존 콘텐츠 형식 (예: "text")는 영역 정의 적용할 수 있습니다. 이 연습에는 정의 개요 영역을 표시 하는 방법을 보여 줍니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-a-managed-extensibility-framework-mef-project"></a>MEF(Managed Extensibility Framework) 프로젝트 만들기  
  
#### <a name="to-create-a-mef-project"></a>MEF 프로젝트를 만들려면  
  
1.  VSIX 프로젝트를 만듭니다. 솔루션 이름을 `OutlineRegionTest`합니다.  
  
2.  편집기 분류자 항목 템플릿을 프로젝트에 추가 합니다. 자세한 내용은 참조 [편집기 항목 템플릿을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-an-editor-item-template.md)합니다.  
  
3.  기존 클래스 파일을 삭제합니다.  
  
## <a name="implementing-an-outlining-tagger"></a>개요 태거 구현  
 개요 영역 종류의 태그도 표시 됩니다 (<xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag>). 이 태그는 표준 동작 개요를 제공 합니다. 윤곽선이 있는 영역을 확장 하거나 축소할 수 있습니다. 확장 되 고 확장 된 영역은 세로 선이 둘러싸여 개요 영역이 축소 된 경우에 더하기 또는 빼기 기호 표시 됩니다.  
  
 다음 단계에는 구분 되는 모든 영역에 대 한 개요 영역을 만드는 한 태거를 정의 하는 방법을 보여 줍니다 "[" 및 "]"입니다.  
  
#### <a name="to-implement-an-outlining-tagger"></a>개요 태거를 구현 하려면  
  
1.  클래스 파일을 추가 하 고 이름을 `OutliningTagger`합니다.  
  
2.  다음 네임 스페이스를 가져옵니다.  
  
     [!code-csharp[VSSDKOutlineRegionTest#1](../extensibility/codesnippet/CSharp/walkthrough-outlining_1.cs)]
     [!code-vb[VSSDKOutlineRegionTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_1.vb)]  
  
3.  이라는 클래스를 만들 `OutliningTagger`, 구현 게 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601>:  
  
     [!code-csharp[VSSDKOutlineRegionTest#2](../extensibility/codesnippet/CSharp/walkthrough-outlining_2.cs)]
     [!code-vb[VSSDKOutlineRegionTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_2.vb)]  
  
4.  텍스트 버퍼 및 스냅숏을 추적 하 고 개요 영역이로 태그를 지정 해야 하는 줄의 집합을 누적 하 일부 필드를 추가 합니다. 이 코드 개요 영역을 나타내는 지역 개체 (을 나중으로 정의 됨) 목록이 포함 됩니다.  
  
     [!code-csharp[VSSDKOutlineRegionTest#3](../extensibility/codesnippet/CSharp/walkthrough-outlining_3.cs)]
     [!code-vb[VSSDKOutlineRegionTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_3.vb)]  
  
5.  버퍼를 구문 분석 하 고 이벤트 처리기를 추가 하는 추가 필드를 초기화 하는 태거 생성자는 <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> 이벤트입니다.  
  
     [!code-csharp[VSSDKOutlineRegionTest#4](../extensibility/codesnippet/CSharp/walkthrough-outlining_4.cs)]
     [!code-vb[VSSDKOutlineRegionTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_4.vb)]  
  
6.  구현 된 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> 태그를 인스턴스화하는 메서드를 확장 합니다. 이 예에서는 가정 하는의 범위는 <xref:Microsoft.VisualStudio.Text.NormalizedSpanCollection> 메서드에 전달 된 항목이이 하지 않더라도 항상 대/소문자를 연속으로 나타납니다. 이 메서드는 각 개요 영역에 대 한 새 태그 범위를 인스턴스화합니다.  
  
     [!code-csharp[VSSDKOutlineRegionTest#5](../extensibility/codesnippet/CSharp/walkthrough-outlining_5.cs)]
     [!code-vb[VSSDKOutlineRegionTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_5.vb)]  
  
7.  선언 된 `TagsChanged` 이벤트 처리기입니다.  
  
     [!code-csharp[VSSDKOutlineRegionTest#6](../extensibility/codesnippet/CSharp/walkthrough-outlining_6.cs)]
     [!code-vb[VSSDKOutlineRegionTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_6.vb)]  
  
8.  추가 `BufferChanged` 에 응답 하는 이벤트 처리기 <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> 텍스트 버퍼를 구문 분석 하 여 이벤트입니다.  
  
     [!code-csharp[VSSDKOutlineRegionTest#7](../extensibility/codesnippet/CSharp/walkthrough-outlining_7.cs)]
     [!code-vb[VSSDKOutlineRegionTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_7.vb)]  
  
9. 버퍼를 구문 분석 하는 메서드를 추가 합니다. 여기에서 설명 하는 예시용 으로만 있습니다. 동기적으로 버퍼 개요 영역을 중첩된으로 구문 분석 합니다.  
  
     [!code-csharp[VSSDKOutlineRegionTest#8](../extensibility/codesnippet/CSharp/walkthrough-outlining_8.cs)]
     [!code-vb[VSSDKOutlineRegionTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_8.vb)]  
  
10. 다음 도우미 메서드는 개요, 수준을 나타냅니다. 1은 가장 왼쪽 중괄호 쌍을 하는 정수를 가져옵니다.  
  
     [!code-csharp[VSSDKOutlineRegionTest#9](../extensibility/codesnippet/CSharp/walkthrough-outlining_9.cs)]
     [!code-vb[VSSDKOutlineRegionTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_9.vb)]  
  
11. 다음 도우미 메서드는 SnapshotSpan (이 항목의 뒷부분에 정의 됨)는 영역으로 변환 합니다.  
  
     [!code-csharp[VSSDKOutlineRegionTest#10](../extensibility/codesnippet/CSharp/walkthrough-outlining_10.cs)]
     [!code-vb[VSSDKOutlineRegionTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_10.vb)]  
  
12. 다음 코드는 예시용 으로만 합니다. 줄 번호 및 개요 영역 및 (있는 경우)는 부모 영역에 대 한 참조의 시작 오프셋을 포함 하는 PartialRegion 클래스를 정의 합니다. 이렇게 하면를 설정 하려면 파서 개요 영역을 중첩 합니다. 파생된 지역 클래스 개요 영역의 끝의 줄 번호에 대 한 참조를 포함합니다.  
  
     [!code-csharp[VSSDKOutlineRegionTest#11](../extensibility/codesnippet/CSharp/walkthrough-outlining_11.cs)]
     [!code-vb[VSSDKOutlineRegionTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_11.vb)]  
  
## <a name="implementing-a-tagger-provider"></a>태거 공급자 구현  
 태거 프로그램에 대 한 태거 공급자를 내보내야 합니다. 태거 공급자가 만드는 `OutliningTagger` "text" 콘텐츠 형식 또는 다른 반환 버퍼에 대 한 프로그램 `OutliningTagger` 버퍼 이미 있는 경우.  
  
#### <a name="to-implement-a-tagger-provider"></a>태거 공급자를 구현 하려면  
  
1.  이라는 클래스를 만들 `OutliningTaggerProvider` 를 구현 하는 <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider>, ContentType 및 TagType 특성을 내보냅니다.  
  
     [!code-csharp[VSSDKOutlineRegionTest#12](../extensibility/codesnippet/CSharp/walkthrough-outlining_12.cs)]
     [!code-vb[VSSDKOutlineRegionTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_12.vb)]  
  
2.  구현 된 <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider.CreateTagger%2A> 메서드를 추가 하 여 프로그램 `OutliningTagger` 버퍼의 속성을 합니다.  
  
     [!code-csharp[VSSDKOutlineRegionTest#13](../extensibility/codesnippet/CSharp/walkthrough-outlining_13.cs)]
     [!code-vb[VSSDKOutlineRegionTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_13.vb)]  
  
## <a name="building-and-testing-the-code"></a>코드 빌드 및 테스트  
 이 코드를 테스트 하려면 OutlineRegionTest 솔루션을 빌드하고 실험적 인스턴스에서 실행 합니다.  
  
#### <a name="to-build-and-test-the-outlineregiontest-solution"></a>빌드하고 OutlineRegionTest 솔루션을 테스트 하려면  
  
1.  솔루션을 빌드합니다.  
  
2.  디버거에서 이 프로젝트를 실행하면 Visual Studio의 두 번째 인스턴스가 인스턴스화됩니다.  
  
3.  텍스트 파일을 만듭니다. 여는 중괄호와 닫는 중괄호 모두 포함 하는 일부 텍스트를 입력 합니다.  
  
    ```  
    [  
       Hello  
    ]  
    ```  
  
4.  두 중괄호를 포함 하는 개요 영역 없어야 합니다. 개요 영역을 축소 하 여는 중괄호의 왼쪽에 빼기 기호를 클릭 하는 할 수 있어야 합니다. 때 영역을 축소 줄임표 (...) 기호 왼쪽에 축소 된 영역 및 텍스트를 포함 하는 팝업 표시 되어야 **텍스트 마우스를 가져가고** 줄임표 위로 포인터를 이동 하면 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 파일 이름 확장명에 콘텐츠 형식 연결](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)