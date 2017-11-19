---
title: "편집기 내부에서 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - architecture
ms.assetid: 822cbb8d-7ab4-40ee-bd12-44016ebcce81
caps.latest.revision: "31"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1876f334ad1b444b464ecc420767dea90baed6b3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="inside-the-editor"></a>편집기 내부에서
편집기는 다양 한 텍스트 보기 및 사용자 인터페이스에서 텍스트 모델 별도로 편집기를 관리 하도록 설계 된 다른 하위 시스템 구성 됩니다.  
  
 이 섹션에서는 편집기의 다양 한 측면에 설명 합니다.  
  
-   [하위 시스템 개요](../extensibility/inside-the-editor.md#overview)  
  
-   [텍스트 모델](../extensibility/inside-the-editor.md#textmodel)  
  
-   [텍스트 보기](../extensibility/inside-the-editor.md#textview)  
  
 이 섹션에서는 편집기의 기능에 설명 합니다.  
  
-   [태그 및 분류자](../extensibility/inside-the-editor.md#tagsandclassifiers)  
  
-   [장식](../extensibility/inside-the-editor.md#adornments)  
  
-   [프로젝션](../extensibility/inside-the-editor.md#projection)  
  
-   [개요](../extensibility/inside-the-editor.md#outlining)  
  
-   [마우스 바인딩](../extensibility/inside-the-editor.md#mousebindings)  
  
-   [편집기 작업](../extensibility/inside-the-editor.md#editoroperations)  
  
-   [IntelliSense](../extensibility/inside-the-editor.md#intellisense)  
  
##  <a name="overview"></a>하위 시스템 개요  
  
### <a name="text-model-subsystem"></a>텍스트 모델 하위 시스템  
 텍스트 모델 하위 시스템은 텍스트를 표현 하 고 해당 조작 사용 하도록 설정 하는 일을 담당 합니다. 텍스트 모델 하위 시스템 포함는 <xref:Microsoft.VisualStudio.Text.ITextBuffer> 편집기에 표시 되는 문자 시퀀스를 설명 하는 인터페이스입니다. 이 텍스트 수정, 추적 및 여러 가지 방법으로 조작할 수입니다. 텍스트 모델 다음과 같은 측면에 대 한 형식을 제공합니다.  
  
-   텍스트 파일을 연결 하 고 읽기와 파일 시스템에 작성을 관리 하는 서비스입니다.  
  
-   개체의 두 시퀀스 간의 최소한의 차이점을 발견 하는 차이점 보관용 서비스입니다.  
  
-   다른 버퍼에 있는 텍스트의 하위 집합 측면에서 버퍼에서 텍스트를 설명 하는 데 사용 되는 시스템입니다.  
  
 텍스트 모델 하위 시스템은 무료 사용자 인터페이스 (UI) 개념입니다. 예를 들어 텍스트 레이아웃 또는 텍스트 서식 지정에 대 한 책임이 없을 있고 텍스트와 연결할 수 있는 시각적 장식 인식 하지 못합니다.  
  
 텍스트 모델 하위 시스템의 public 형식은.NET Framework 기본 클래스 라이브러리 및는 프레임 워크 MEF (Managed Extensibility)에 종속 될 Microsoft.VisualStudio.Text.Data.dll 및 Microsoft.VisualStudio.CoreUtilitiy.dll에 포함 됩니다.  
  
### <a name="text-view-subsystem"></a>텍스트 보기 하위 시스템  
 텍스트 보기 하위 시스템은 서식 및 텍스트를 표시 하는 일을 담당 합니다. 이 하위 시스템에 있는 형식 형식 Windows Presentation Foundation (WPF)에 의존 하는 여부에 따라 두 계층으로 나뉩니다. 가장 중요 한 형식은 <xref:Microsoft.VisualStudio.Text.Editor.ITextView> 및 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView>, 집합을 표시 하도록 텍스트 줄의 캐럿, 선택 영역 및 WPF UI 요소를 사용 하 여 텍스트를 표시 하기 위한 기능을 제어 하 합니다. 이 하위 시스템 제공 텍스트 주위의 여백 영역을 표시 합니다. 이러한 여백 확장 될 수 있습니다 및 다른 종류의 콘텐츠 및 시각적 효과 포함할 수 있습니다. 여백에 줄 번호 표시 및 스크롤 막대는 있습니다.  
  
 텍스트 보기 하위 시스템의 public 형식 Microsoft.VisualStudio.Text.UI.dll 및 Microsoft.VisualStudio.Text.UI.Wpf.dll에 포함 됩니다. 첫 번째 플랫폼 독립적인 요소를 포함 하 고 두 번째 WPF 관련 요소를 포함 합니다.  
  
### <a name="classification-subsystem"></a>분류 하위 시스템  
 분류 하위 시스템은 텍스트에 대 한 글꼴 속성을 결정 합니다. 분류자 "키워드" 또는 "주석" 예를 들어 다른 클래스에는 텍스트를 나눕니다. 분류 서식 맵에 관련이 이러한 클래스 실제 글꼴 속성을 예를 들어 "Blue Consolas 10pt"입니다. 이 정보는 포맷 하 고 텍스트를 렌더링 하는 경우 텍스트 보기에서 사용 됩니다. 태그 지정, 텍스트의 범위와 연결 되도록 데이터를 사용 하면이 항목의 뒷부분에 자세히 설명 되어 있습니다.  
  
 분류 하위 시스템의 공용 유형이 Microsoft.VisualStudio.Text.Logic.dll에 포함 되어 및 Microsoft.VisualStudio.Text.UI.Wpf.dll에 포함 된 분류의 시각적 측면 상호 작용 합니다.  
  
### <a name="operations-subsystem"></a>작업 하위 시스템  
 작업 하위 시스템 편집기 동작을 정의합니다. 실행 취소 시스템 및 Visual Studio 편집기 명령에 대 한 구현을 제공합니다.  
  
## <a name="a-closer-look-at-the-text-model-and-the-text-view"></a>텍스트 모델 및 텍스트 보기 자세히 보기  
  
###  <a name="textmodel"></a>텍스트 모델  
 텍스트 모델 하위 시스템은 텍스트 종류의 다른 그룹으로 구성 됩니다. 여기에 텍스트 버퍼, 텍스트 스냅숏 및 텍스트 범위 포함 됩니다.  
  
#### <a name="text-buffers-and-text-snapshots"></a>텍스트 버퍼 및 텍스트 스냅숏  
 <xref:Microsoft.VisualStudio.Text.ITextBuffer> 인터페이스는 인코딩을 사용 하 여 u t F-16을 사용 하 여 인코딩된 유니코드 문자 시퀀스로 나타냅니다는 `String` .NET Framework의 형식입니다. 파일 시스템 문서로 텍스트 버퍼를 유지할 수 있지만 필요 하지 않습니다.  
  
 <xref:Microsoft.VisualStudio.Text.ITextBufferFactoryService> 빈 텍스트 버퍼 또는 또는 문자열에서 초기화 되는 텍스트 버퍼를 만드는 데 <xref:System.IO.TextReader>합니다. 텍스트 버퍼를 파일 시스템으로 계속 표시 될 수는 <xref:Microsoft.VisualStudio.Text.ITextDocument>합니다.  
  
 에서는 텍스트 버퍼의 소유권을 호출 하 여 스레드가 될 때까지 스레드 텍스트 버퍼를 편집할 수 있습니다 <xref:Microsoft.VisualStudio.Text.ITextBuffer.TakeThreadOwnership%2A>합니다. 그런 다음 해당 스레드만 편집을 수행할 수 있습니다.  
  
 텍스트 버퍼의 수명 동안 여러 버전을 통과할 수 있습니다. 새 버전은 생성 된 할 때마다 버퍼를 편집 및는 변경할 수 없는 <xref:Microsoft.VisualStudio.Text.ITextSnapshot> 버퍼의 해당 버전의 내용을 나타냅니다. 텍스트 스냅숏을 변경할 수 없기 때문에 나타내는 텍스트 버퍼 계속 변경 하는 경우에 텍스트 스냅숏으로 제한 없이 모든 스레드에서 액세스할 수 있습니다.  
  
#### <a name="text-snapshots-and-text-snapshot-lines"></a>텍스트 스냅숏 및 스냅숏 줄 텍스트  
 문자 시퀀스 또는 줄의 시퀀스로 텍스트 스냅숏의 내용을 볼 수 있습니다. 문자와 줄 모두 인덱스 0부터 시작 됩니다. 빈 텍스트 스냅숏 0 개의 문자 및 한 빈 줄을 포함합니다. 유효한 유니코드 줄 바꿈 문자 시퀀스를 나 시작 또는 버퍼의 끝 줄 구분 됩니다. 줄 바꿈 문자가 텍스트 스냅숏에서 명시적으로 표현 되 고 텍스트 스냅숏의 줄 바꿈 일부만 필요가 동일 합니다.  
  
> [!NOTE]
>  Visual Studio 편집기에서 줄 바꿈 문자에 대 한 자세한 내용은 참조 [인코딩 및 줄 바꿈](../ide/encodings-and-line-breaks.md)합니다.  
  
 텍스트 줄으로 표시 됩니다는 <xref:Microsoft.VisualStudio.Text.ITextSnapshotLine> 특정 줄 번호에 대 한 또는 특정 문자 위치에 대 한 텍스트 스냅숏에서 가져올 수 있는 개체입니다.  
  
#### <a name="snapshotpoints-snapshotspans-and-normalizedsnapshotspancollections"></a>SnapshotPoints, SnapshotSpans, 및 NormalizedSnapshotSpanCollections  
 A <xref:Microsoft.VisualStudio.Text.SnapshotPoint> 스냅숏으로의 문자 위치를 나타냅니다. 위치는 0에서 스냅숏의 길이 사이 포함 하도록 보장 됩니다. A <xref:Microsoft.VisualStudio.Text.SnapshotSpan> 스냅숏에 있는 텍스트 범위를 나타냅니다. 끝 위치는 0에서 스냅숏의 길이 사이 포함 하도록 보장 됩니다. <xref:Microsoft.VisualStudio.Text.NormalizedSnapshotSpanCollection> 의 집합으로 구성 <xref:Microsoft.VisualStudio.Text.SnapshotSpan> 동일한 스냅숏에서 개체입니다.  
  
#### <a name="spans-and-normalizedspancollections"></a>범위 및 NormalizedSpanCollections  
 A <xref:Microsoft.VisualStudio.Text.Span> 텍스트 스냅숏에 있는 텍스트 범위에 적용할 수 있는 간격을 나타냅니다. 범위는 0을 포함 하 여 모든 위치에서 시작할 수 있도록 스냅숏 위치는 0부터 시작 합니다. `End` 범위의 속성은의 합계에는 `Start` 속성 및 해당 `Length` 속성입니다. A `Span` 로 인덱싱된 문자를 포함 하지 않습니다는 `End` 속성입니다. 가 시작 하는 범위 예를 들어 = 5, 길이 = 3에 끝이 = 8, 5, 6 및 7 위치에 문자를 포함 합니다. 이 범위에 대 한 표기법은 5..8) 합니다.  
  
 두 범위에 있는 경우 모든 위치에서 공통적으로 끝 위치를 포함 하 여 교차 합니다. 따라서 교차 [3, 5) 및 [2, 7)는 [3, 5) 및 교차 [3, 5) 및 [5, 7)는 [5, 5)). (다음에 유의 [5, 5)는 빈 범위입니다.)  
  
 두 범위는 위치가 공통 끝 위치를 제외한 경우 겹쳐서 표시 합니다. 빈 범위 다른 범위를 중첩 되지 하 고 두 범위가 겹치는 비어 있을 수 있습니다.  
  
 A <xref:Microsoft.VisualStudio.Text.NormalizedSpanCollection> 해당 범위의 시작 속성 순서 대로 범위 목록입니다. 목록에서 중복 되거나 인접 범위 병합 됩니다. 예를 들어 범위 집합을 부여 [5..9), [0..1), [3..6), 및 [9..10), 범위 정규화 된 목록은 [0..1), [3..10) 합니다.  
  
#### <a name="itextedit-textversion-and-text-change-notifications"></a>ITextEdit, TextVersion 및 텍스트 변경 알림  
 텍스트 버퍼의 내용을 사용 하 여 변경할 수 있습니다는 <xref:Microsoft.VisualStudio.Text.ITextEdit> 개체입니다. 이러한 개체를 만드는 (중 하나를 사용 하 여는 `CreateEdit()` 방식의 <xref:Microsoft.VisualStudio.Text.ITextBuffer>)의 텍스트 편집으로 구성 된 텍스트 트랜잭션을 시작 합니다. 모든 편집은 문자열 버퍼에서 텍스트의 일부 범위 대체 합니다. 트랜잭션이 시작 될 때 좌표와의 모든 편집 내용을 버퍼의 스냅숏을 기준으로 표시 됩니다. <xref:Microsoft.VisualStudio.Text.ITextEdit> 개체가 동일한 트랜잭션 내에서 다른 편집의 영향을 받는 편집의 좌표를 조정 합니다.  
  
 예를 들어이 문자열을 포함 하는 텍스트 버퍼를 것이 좋습니다.  
  
```  
abcdefghij  
```  
  
 두 개의 편집에서 범위를 대체 하는 하나의 편집을 포함 하는 트랜잭션은 적용 [2..4) 문자를 사용 하 여 `X` 에서 범위를 대체 하는 두 번째 편집 [6..9) 문자를 사용 하 여 `Y`합니다. 결과이 버퍼.  
  
```  
abXefYj  
```  
  
 두 번째 편집에 대 한 좌표는 첫 번째 편집 내용이 적용 하기 전에 트랜잭션의 시작 부분에서 버퍼의 내용에 대해 계산 된 합니다.  
  
 버퍼에 변경 내용이 적용 때는 <xref:Microsoft.VisualStudio.Text.ITextEdit> 개체를 호출 하 여 커밋합니다 해당 `Apply()` 메서드. 하나 이상의 비어 있지 않은 편집 하는 경우 새 <xref:Microsoft.VisualStudio.Text.ITextVersion> 만들어지면 새 <xref:Microsoft.VisualStudio.Text.ITextSnapshot> 만들어지면 하나의 `Changed` 이벤트가 발생 합니다. 모든 텍스트 버전이 서로 다른 텍스트 스냅숏입니다. 텍스트 버전 설명 변경 내용만 하나의 스냅숏에서 다음 이지만 텍스트 스냅숏에 대해 편집 트랜잭션을 후 텍스트 버퍼의 전체 상태를 나타냅니다. 일반적으로 텍스트 스냅숏은 한 번으로 사용 하려는 및 텍스트 버전 일정 시간 동안 활성 상태로 유지 되어야 하는 동안 다음 삭제 합니다.  
  
 텍스트 버전이 포함 된 <xref:Microsoft.VisualStudio.Text.INormalizedTextChangeCollection>합니다. 이 컬렉션에는 변경 내용을 설명 하는, 스냅숏을 적용 하면 후속 스냅숏을 생성 합니다. 모든 <xref:Microsoft.VisualStudio.Text.ITextChange> 컬렉션의 변경, 대체 문자열 및 대체 문자열의 문자 위치를 포함 합니다. 바꾼된 문자열 기본 삽입을 위해 비어 있고 대체 문자열 기본 삭제에 대 한 비어 있습니다. 정규화 된 컬렉션은 항상 `null` 텍스트 버퍼의 가장 최신 버전에 대 한 합니다.  
  
 하나의 <xref:Microsoft.VisualStudio.Text.ITextEdit> 언제 든 지는 텍스트 버퍼에 대 한 개체를 인스턴스화할 수 하 고 모든 텍스트 편집 내용을 (소유권 주장 된) 경우 텍스트 버퍼를 소유 하는 스레드에서 수행 해야 합니다. 텍스트 편집을 호출 하 여 중단 수 해당 `Cancel` 메서드 또는 해당 `Dispose` 메서드.  
  
 <xref:Microsoft.VisualStudio.Text.ITextBuffer>또한 제공 `Insert()`, `Delete()`, 및 `Replace()` 비슷한 메서드가 <xref:Microsoft.VisualStudio.Text.ITextEdit> 인터페이스입니다. 만드는 것과 같은 효과가 이러한 호출 프로그램 <xref:Microsoft.VisualStudio.Text.ITextEdit> 개체는 비슷한 호출을 실행 한 다음 편집을 적용 합니다.  
  
#### <a name="tracking-points-and-tracking-spans"></a>추적 지점 및 추적 범위  
 <xref:Microsoft.VisualStudio.Text.ITrackingPoint> 텍스트 버퍼의 문자 위치를 나타냅니다. 바꾸려는 문자의 위치를 발생 시키는 방식으로 버퍼를 편집한, 추적 지점을 함께 이동 합니다. 예를 들어 추적 지점은 10 버퍼의 위치를 참조 하는 경우 5 개 문자 버퍼의 시작 부분에 삽입 됩니다 추적 지점을 다음 위치를 나타냅니다 15. 해당 동작은에 의해 결정 됩니다 정확 하 게 추적 지점을 가리키는 위치에 삽입 된 경우 해당 <xref:Microsoft.VisualStudio.Text.PointTrackingMode>, 될 수 있습니다 `Positive` 또는 `Negative`합니다. 삽입;의 끝에는 이제 된 같은 문자를 추적 지점에서 참조 된 추적 모드 양수 이면 추적 모드 음수 이면 추적 지점에서 원래 위치에 삽입 된 첫 번째 문자를 참조 합니다. 추적 지점을 나타내는 위치에 있는 문자가 삭제 되 면 추적 지점을 삭제 범위의 뒤에 오는 첫 번째 문자로 이동 합니다. 예를 들어 추적 지점 위치 5에 있는 문자가 나타내며 3-6 위치의 문자 삭제를 추적 지점 위치 3에 있는 문자를 참조 합니다.  
  
 <xref:Microsoft.VisualStudio.Text.ITrackingSpan> 하나만 위치 대신 문자 범위를 나타냅니다. 해당 동작은 따라 사용자가 해당 <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>합니다. 범위 추적 모드가 이면 <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, 범위 추적 모드가 이면 가장자리가; 삽입 된 텍스트를 통합 하는 추적 범위 증가 <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, 추적 범위 가장자리에 삽입 하는 텍스트를 포함 되지 않습니다. 그러나 범위 추적 모드를 사용 하는 경우 <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, 삽입, 처음으로 현재 위치를 푸시합니다 경우 범위 추적 모드 <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, 삽입 끝으로 현재 위치를 푸시합니다.  
  
 소속 된 텍스트 버퍼의 모든 스냅숏에 대 한 추적 지점 위치 또는 추적 범위의 범위를 가져올 수 있습니다. 추적 지점 및 추적 범위 모든 스레드에서 안전 하 게 참조 될 수 있습니다.  
  
#### <a name="content-types"></a>콘텐츠 형식  
 콘텐츠 유형은 여러 종류의 콘텐츠를 정의 하기 위한 메커니즘입니다. 콘텐츠 형식 "text", "code" 또는 "binary" 등의 파일 형식 또는 "xml", "vb" 또는 "c#"와 같은 기술 형식을 수 있습니다. 예를 들어 C# 및 Visual Basic 모두 있지만 다른 프로그래밍 언어에 없는 키워드는 단어 "using"입니다. 따라서이 키워드의 정의 "c#" 및 "vb" 콘텐츠 형식으로 제한 됩니다.  
  
 콘텐츠 형식은 장식 및 편집기의 다른 요소에 대 한 필터로 사용 됩니다. 많은 편집기 기능 및 확장 지점 콘텐츠 형식; 별로 정의 됩니다. 예를 들어 텍스트 색은 일반 텍스트 파일, XML 파일 및 Visual Basic 소스 코드 파일에 대 한 다릅니다. 일반적으로 텍스트 버퍼는 만들어질 때 텍스트 버퍼의 콘텐츠 형식을 변경할 수 있습니다 콘텐츠 형식을 할당 해야 합니다.  
  
 콘텐츠 형식을 여러-형식에서 상속할 수 다른 콘텐츠입니다. <xref:Microsoft.VisualStudio.Utilities.ContentTypeDefinition> 여러 기본 형식이 지정된 된 콘텐츠 형식의 부모로 지정할 수 있습니다.  
  
 개발자가 자체 콘텐츠 형식 정의 업데이트 하 고를 사용 하 여 등록할 수는 <xref:Microsoft.VisualStudio.Utilities.IContentTypeRegistryService>합니다. 사용 하 여 특정 콘텐츠 형식에 대해 다양 한 편집기 기능을 정의할 수 있습니다는 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>합니다. 예를 들어, 편집기 여백, 장식 및 마우스 처리기 정의할 수 있습니다 특정 콘텐츠 형식을 표시 하는 편집기에만 적용 되도록 합니다.  
  
###  <a name="textview"></a>텍스트 보기  
 모델 뷰 컨트롤러 (MVC) 패턴의 보기 부분 뷰, 그래픽 요소를 스크롤 막대의 캐럿 등의 서식을 텍스트 보기를 정의 합니다. Visual Studio 편집기의 모든 프레젠테이션 요소는 WPF를 기반으로 합니다.  
  
#### <a name="text-views"></a>텍스트 보기  
 <xref:Microsoft.VisualStudio.Text.Editor.ITextView> 인터페이스 텍스트 보기의 플랫폼 독립적인 표현입니다. 텍스트 문서 창에 표시 하는 데 주로 사용 하지만 사용할 수 있습니다 다른 용도 대 한 예를 들어 도구 설명에.  
  
 텍스트 보기에는 다양 한 종류의 텍스트 버퍼의 참조합니다. <xref:Microsoft.VisualStudio.Text.Editor.ITextView.TextViewModel%2A> 속성은 참조는 <xref:Microsoft.VisualStudio.Text.Editor.ITextViewModel> 이러한 세 개의 다른 텍스트 버퍼를 가리키는 개체: 최상위 데이터 수준의 버퍼 편집 버퍼 발생는 편집 하 고 버퍼를 시각적 버퍼에서 데이터 버퍼를 텍스트 보기에 표시 합니다.  
  
 텍스트 내부 텍스트 버퍼에 연결 하는 분류자에 따라 서식이 지정 되어 있으며 텍스트 뷰 자체에 연결 되어 있는 장식 공급자를 사용 하 여 표시 합니다.  
  
#### <a name="the-text-view-coordinate-system"></a>텍스트 보기 좌표계  
 텍스트 보기 좌표계 텍스트 보기에서 위치를 지정합니다. 이 좌표 시스템을 0.0 x 값이 표시 되는 텍스트의 왼쪽된 가장자리에 해당 하 고 y 값 0.0 표시 되는 텍스트의 위쪽 가장자리에 해당 합니다. 왼쪽에서 오른쪽으로 증가 하 한 x 좌표 및 y 좌표 위쪽에서 아래쪽으로 증가 합니다.  
  
 뷰포트 (텍스트 창에 표시 되는 텍스트의 일부) 가로로 스크롤할 수 동일한 방식으로 세로로 스크롤 된 대로 합니다. 뷰포트 기준 그리기 화면으로 이동 하는 왼쪽된 좌표를 변경 하 여 가로 방향으로 스크롤됩니다. 그러나 뷰포트 스크롤할 수 있는 수직으로 렌더링된 된 텍스트를 변경한 경우에는 <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> 이벤트를 발생 합니다.  
  
 좌표계에서 거리 논리 픽셀에 해당합니다. 텍스트 렌더링 화면 크기 조정 변환 없이 표시 되 면 렌더링 텍스트 좌표계에서 하나의 단위 디스플레이에서 하나의 픽셀에 해당 합니다.  
  
#### <a name="margins"></a>여백  
 <xref:Microsoft.VisualStudio.Text.Editor.ITextViewMargin> 인터페이스 여백을 나타내며 여백과 크기의 표시 방식 제어를 수 있습니다. "위쪽", "왼쪽", "오른쪽" 및 "아래쪽" 라고 하며 위쪽, 아래쪽, 왼쪽 또는 보기의 오른쪽 가장자리에 연결 되어 있는 네 가지 미리 정의 된 여백 가지가 있습니다. 이러한 여백은 컨테이너 다른 여백과 배치할 수 있습니다. 인터페이스의 여백 크기 및 여백의 표시 유형을 반환 하는 메서드를 정의 합니다. 여백은 연결 되어 있는 텍스트 보기에 대 한 추가 정보를 제공 하는 시각적 요소입니다. 예를 들어, 줄 번호 여백 텍스트 보기에 대 한 줄 번호를 표시합니다. 문자 모양 여백 UI 요소를 표시 합니다.  
  
 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewMarginProvider> 인터페이스 만들기 및 여백의 배치를 처리 합니다. 여백이 다른 여백과 기준으로 정렬할 수 있습니다. 우선 순위가 높은 여백은 텍스트 보기에 가깝게 위치입니다. 예를 들어 두 왼쪽된 여백, 여백 A 및 B, 여백 및 여백을 B 보다 우선 순위가 낮은 여백 A, B 여백이 나타납니다 왼쪽의 여백 1.  
  
#### <a name="the-text-view-host"></a>텍스트 보기 호스트  
 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> 텍스트 보기 및 보기, 예를 들어, 스크롤 막대를 함께 사용 해야 하는 모든 인접 장식 인터페이스를 포함 합니다. 텍스트 보기 호스트에는 보기의 테두리에 연결 되어 있는 여백을 포함 되어 있습니다.  
  
#### <a name="formatted-text"></a>서식 있는 텍스트  
 텍스트 보기에 표시 되는 텍스트는 이루어져 <xref:Microsoft.VisualStudio.Text.Formatting.ITextViewLine> 개체입니다. 모든 텍스트 보기 줄 텍스트 보기에는 텍스트 한 줄에 해당합니다. 기본 텍스트 버퍼의 긴 줄 수 있습니다 수 부분 (자동 줄 바꿈을 사용 하지 않는) 하는 경우를 려 지기 또는 여러 텍스트 보기 줄으로 나뉘어집니다. <xref:Microsoft.VisualStudio.Text.Formatting.ITextViewLine> 메서드 및 속성을 행으로 연결할 수 있는 장식 및 좌표 문자와 간의 매핑을 대 한 인터페이스를 포함 합니다.  
  
 <xref:Microsoft.VisualStudio.Text.Formatting.ITextViewLine>사용 하 여 개체가 생성 된 <xref:Microsoft.VisualStudio.Text.Formatting.IFormattedLineSource> 인터페이스입니다. 현재 보기에 표시 되는 텍스트에만 관심이, 서식의 원본을 무시할 수 있습니다. 되지 않은 텍스트를 형식에 관심이 있는 경우 (예: 서식 있는 텍스트 잘라내기 지원 하 여 붙여 넣는), 보기에 표시 하면 צ ְ ײ <xref:Microsoft.VisualStudio.Text.Formatting.IFormattedLineSource> 텍스트 버퍼에서 텍스트의 서식 합니다.  
  
 텍스트 보기 형식을 하나 지정 <xref:Microsoft.VisualStudio.Text.ITextSnapshotLine> 한 번에 있습니다.  
  
## <a name="editor-features"></a>편집기 기능  
 편집기의 기능에는 기능의 정의 구현에서 별도 있도록 설계 됩니다. 편집기에는 이러한 기능이 포함 됩니다.  
  
-   태그 및 분류자  
  
-   장식  
  
-   프로젝션  
  
-   개요  
  
-   마우스 및 키 바인딩  
  
-   작업 및 기본 형식  
  
-   IntelliSense  
  
###  <a name="tagsandclassifiers"></a>태그 및 분류자  
 태그는 텍스트 범위와 연결 된 표식입니다. 제공할 수 다양 한 방법으로 예를 들어 텍스트 색, 밑줄, 그래픽 또는 팝업을 사용 하 여 합니다. 분류자는 한 종류의 태그입니다.  
  
 다른 종류의 태그는 <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag> 텍스트 강조 표시에 대 한 <xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag> 개요에 대 한 및 <xref:Microsoft.VisualStudio.Text.Tagging.ErrorTag> 컴파일 오류에 대 한 합니다.  
  
#### <a name="classification-types"></a>분류 유형  
 <xref:Microsoft.VisualStudio.Text.Classification.IClassificationType> 인터페이스의 텍스트는 추상 종류는 동급 클래스를 나타냅니다. 분류 유형을 여러-형식에서 상속할 수 다른 분류 합니다. 예를 들어, 프로그래밍 언어 분류 포함 될 수 있습니다 "키워드", "comment" 및 "식별자"는 모두 "코드"에서 상속 합니다. "명사", "동사" 및 "형용사" 모두 "자연어"에서 상속 된 자연어 분류 유형이 포함할 수 있습니다.  
  
#### <a name="classifications"></a>분류  
 분류는 텍스트 범위를 통해 일반적으로 특정 분류 형식의 인스턴스입니다. A <xref:Microsoft.VisualStudio.Text.Classification.ClassificationSpan> 분류를 나타내기 위해 사용 됩니다. 이 텍스트 범위는 특정 분류 형식 시스템에 알려줍니다 텍스트의 특정 범위를 포함 하는 레이블로 분류 범위 생각할 수 있습니다.  
  
#### <a name="classifiers"></a>분류자  
 <xref:Microsoft.VisualStudio.Text.Classification.IClassifier> 는 텍스트 분류의 집합으로 중단 하는 메커니즘입니다. 분류자 특정 콘텐츠 형식에 대해 정의 하 고 특정 텍스트 버퍼에 대 한 인스턴스화할 해야 합니다. 클라이언트를 구현 해야 <xref:Microsoft.VisualStudio.Text.Classification.IClassifier> 텍스트 분류에 참여할 수 있습니다.  
  
#### <a name="classifier-aggregators"></a>분류자 수집기  
 분류자 집계는 하나의 텍스트 버퍼에 대 한 모든 분류자 분류를 하나의 집합으로 결합 하는 메커니즘입니다. 예를 들어 C# 분류자와 영어 분류자 수 C# 파일에 주석을 통해 분류를 만듭니다. 이 주석은 고려해 야 합니다.  
  
```  
// This method produces a classifier  
```  
  
 C# 분류자 수을 주석으로 전체 범위 레이블과 영어 분류자 수 분류 합니다. "생성"는 "동사" 및 "method"는 "명사"로 합니다. 겹치지 않는 분류의 집합을 생성 하는 집계 및 집합의 유형을 기반으로 전체 기여입니다.  
  
 분류자 집계를 분류의 집합으로 텍스트를 나눕니다 때문에 분류자 이기도 합니다. 분류자 집계도 있는지 여부를 확인 있습니다 사용할 수 있는 분류 겹치는 분류 정렬 됩니다. 개별 분류자 순서에 관계 없이, 분류, 집합이 반환 되며 어떤 방식으로든에서 겹치는 있습니다.  
  
#### <a name="classification-formatting-and-text-coloring"></a>분류 서식 및 텍스트 색  
 텍스트 서식 지정은 한 예는 텍스트 분류를 기반으로 하는 기능입니다. 응용 프로그램에서 텍스트 표시를 확인 하려면 텍스트 보기 계층에 의해 사용 됩니다. 텍스트 서식 지정 영역은 WPF에 종속 이지만 분류 논리 정의 되었습니다.  
  
 분류 형식이 서식 특정 분류 형식에 대 한 속성 집합입니다. 이러한 형식은 분류 유형 부모 형식에서 상속합니다.  
  
 <xref:Microsoft.VisualStudio.Text.Classification.IClassificationFormatMap> 텍스트 서식 지정 속성의 집합으로 분류 유형에서 지도입니다. 편집기에서 서식 맵에 구현 분류 형식의 모든 내보내기를 처리합니다.  
  
###  <a name="adornments"></a>장식  
 장식을 직접 관련이 없는 글꼴 및 색 텍스트 보기에 있는 문자의 그래픽 효과. 예를 들어 여러 프로그래밍 언어에서 비 컴파일 코드를 표시 하는 데 사용 되는 빨간색 물결선 밑줄이 있는 포함 된 장식이 이며 도구 설명 팝업 장식 됩니다. 파생 된 장식을 <xref:System.Windows.UIElement> 구현 및 <xref:Microsoft.VisualStudio.Text.Tagging.ITag>합니다. 두 가지 특수 한 유형의 장식 태그는는 <xref:Microsoft.VisualStudio.Text.Tagging.SpaceNegotiatingAdornmentTag>, 뷰의 텍스트와 동일한 공간을 차지 하는 장식을 대 한 고 <xref:Microsoft.VisualStudio.Text.Tagging.ErrorTag>, 물결선 밑줄에 대 한 합니다.  
  
 포함 된 장식을 서식 있는 텍스트 보기의 일부를 구성 하는 그래픽입니다. 다른 Z-순서 계층에 구성 된 합니다. 다음과 같이 세 개의 기본 제공 계층 가지 있습니다: 텍스트, 캐럿 및 선택 합니다. 그러나 개발자가 더욱 더 많은 레이어를 정의 하 고 서로 기준으로 순서 대로 배치 수입니다. 장식 포함 된 세 가지는 상대 텍스트 장식 (있음 텍스트를 움직이면 이동 되며 텍스트를 삭제 해도 삭제), (해야 하는 텍스트가 아닌 부분 뷰를 사용 하 여 수행할)의 보기 상대 장식 및 소유자 제어 장식 ( 개발자 관리 해야 해당 배치).  
  
 팝업 장식 텍스트 보기, 예: 도구 설명 위에 작은 창에 표시 되는 그래픽 됩니다.  
  
###  <a name="projection"></a>프로젝션  
 프로젝션은 다양 한 유형의 실제로 텍스트를 저장 하지 않지만, 대신 다른 텍스트 버퍼에서 텍스트를 결합 하는 텍스트 버퍼를 생성 하기 위한 기술입니다. 예를 들어 다른 두 개의 버퍼에서 텍스트를 하나의 버퍼에 말 이죠 결과 표시 하거나를 하나의 버퍼에서 텍스트의 부분을 숨길 프로젝션 버퍼를 사용할 수 있습니다. 프로젝션 버퍼를 다른 프로젝션 버퍼 소스 버퍼 작동할 수 있습니다. 다양 한 방법으로 텍스트를 다시 정렬 하려면 프로젝션 별로 관련 된 버퍼 집합을 생성할 수 있습니다. (이러한 집합을 프로젝트는 *버퍼 그래프*.) Visual Studio 텍스트 개요 기능을 축소 된 텍스트를 숨기려면 프로젝션 버퍼를 사용 하 여 구현 됩니다 및 ASP.NET 페이지에 대 한 Visual Studio 편집기는 Visual Basic 및 C#과 같은 포함 된 언어를 지원 하기 위해 도법을 사용 합니다.  
  
 <xref:Microsoft.VisualStudio.Text.Projection.IProjectionBuffer> 사용 하 여 만든 <xref:Microsoft.VisualStudio.Text.Projection.IProjectionBufferFactoryService>합니다. 정렬된 된 시퀀스를 나타내는 프로젝션 버퍼 <xref:Microsoft.VisualStudio.Text.ITrackingSpan> 이라고 하는 개체 *소스 범위*합니다. 이러한 범위의 내용은 일련의 문자로 표시 됩니다. 소스 범위 그려집니다 텍스트 버퍼 라고 *버퍼 원본*합니다. 프로젝션 버퍼의 클라이언트는 일반 텍스트 버퍼에서와 다른 점에 유의 필요가 없습니다.  
  
 프로젝션 버퍼 소스 버퍼에서 텍스트 변경 이벤트를 수신합니다. 변경 내용에는 원본에 있는 텍스트 범위, 프로젝션 버퍼 자체 좌표로 변경 된 텍스트 좌표를 매핑하고 적절 한 텍스트 변경 이벤트를 발생 시킵니다. 예를 들어, 이러한 내용이 들어 있는 소스 버퍼를 A와 B는 것이 좋습니다.  
  
```  
A: ABCDE  
B: vwxyz  
```  
  
 하나는 및 버퍼의 모두 들어 있는 다른 모두 들어 있는 버퍼 B의 두 텍스트 범위에서 프로젝션 버퍼 P 형식이 P에는 다음 내용이:  
  
```  
P: ABCDEvwxyz  
```  
  
 경우 부분 문자열 `xy` P 버퍼를 나타내는 위치 7과 8에 문자가 삭제 된 이벤트를 발생 시킵니다. 버퍼 B에서에서 삭제 됩니다.  
  
 프로젝션 버퍼를 직접 편집할 수도 있습니다. 적절 한 소스 버퍼에 대 한 편집 전파 합니다. 예를 들어 문자열 (문자 "v"의 원래 위치) 6 위치의 P 버퍼에 삽입 되 면 삽입 위치 1에서 버퍼 B에 전파 됩니다.  
  
 프로젝션 버퍼에 기여 하는 소스 범위에 제한이 있습니다. 소스 범위와 겹치지 않을 수 있습니다. 프로젝션 버퍼의 위치는 모든 소스 버퍼에 둘 이상의 위치에 매핑할 수 없습니다 및 소스 버퍼의 위치를 프로젝션 버퍼에 둘 이상의 위치에 매핑할 수 없습니다. 소스 버퍼 관계 없는 circularities 허용 됩니다.  
  
 이벤트 소스 집합이 버퍼링 프로젝션 버퍼 변경 하 고 변경 내용을 원본 집합에 걸쳐 있는 경우 발생 합니다.  
  
 생략 버퍼는 프로젝션 버퍼의 특수 한 종류입니다. 개요에 대 한 확장 및 텍스트 블록을 축소 하는 작업에 주로 사용 됩니다. 생략 버퍼 하나만 소스 버퍼를 기반으로 하며 생략 버퍼의 범위 순서를 지정 해야 동일 따라 소스 버퍼에 정렬 됩니다.  
  
##### <a name="the-buffer-graph"></a>버퍼 그래프  
 <xref:Microsoft.VisualStudio.Text.Projection.IBufferGraph> 프로젝션 버퍼에 대 한 그래프에서 인터페이스에 매핑할 수 있도록 합니다. 모든 텍스트 버퍼 및 프로젝션 버퍼는 언어 컴파일러에서 생성 되는 추상 구문 트리 매우 유사 하 게 지정된 된 비순환 그래프에 수집 됩니다. 그래프는 모든 텍스트 버퍼 될 수 있는 최상위 버퍼에 의해 정의 됩니다. 최상위 버퍼 소스 버퍼의 지점에의 한 지점에서 또는 소스 버퍼의 범위 집합을 top 버퍼의 범위에서 버퍼 그래프 매핑할 수 있습니다. 마찬가지로, 맵는 포인트 하거나 소스 버퍼에서 최상위 버퍼의 지점에 걸쳐 있을 수 있습니다. 버퍼 그래프를 사용 하 여 생성 됩니다는 <xref:Microsoft.VisualStudio.Text.Projection.IBufferGraphFactoryService>합니다.  
  
##### <a name="events-and-projection-buffers"></a>이벤트 및 프로젝션 버퍼  
 프로젝션 버퍼를 수정한 경우 수정 작업에 종속 된 버퍼에 프로젝션 버퍼에서 전송 됩니다. 모든 버퍼를 수정한 후 버퍼 변경 이벤트가 발생 되 면 가장 범위가 큰 버퍼를 시작 합니다.  
  
###  <a name="outlining"></a>개요  
 개요 확장 또는 다양 한 텍스트 보기에 텍스트 블록을 축소 하는 기능입니다. 일종으로 정의 되어 개요의 <xref:Microsoft.VisualStudio.Text.Tagging.ITag>에서 같은 방식으로 장식 정의 됩니다. A <xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag> 확장 하거나 축소할 수 있는 텍스트 영역을 정의 하는 태그입니다. 개요 기능을 사용 하려면 가져와야는 <xref:Microsoft.VisualStudio.Text.Outlining.IOutliningManagerService> 가져오려는 <xref:Microsoft.VisualStudio.Text.Outlining.IOutliningManager>합니다. 개요 관리자 열거, 축소 하 고 다른 블록으로 표시 되는 확장 <xref:Microsoft.VisualStudio.Text.Outlining.ICollapsible> 개체, 및 그에 따라 이벤트를 발생 시킵니다.  
  
###  <a name="mousebindings"></a>마우스 바인딩  
 마우스 바인딩에 서로 다른 명령에 마우스 움직임을 연결합니다. 마우스 바인딩을 사용 하 여 정의 <xref:Microsoft.VisualStudio.Text.Editor.IMouseProcessorProvider>와 키 바인딩을 사용 하 여 정의 되는 <xref:Microsoft.VisualStudio.Text.Editor.IKeyProcessorProvider>합니다. <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> 자동으로 모든 바인딩은 인스턴스화하고 보기의 마우스 이벤트에 연결 합니다.  
  
 <xref:Microsoft.VisualStudio.Text.Editor.IMouseProcessor> 인터페이스 여러 마우스 이벤트에 대 한 전처리 및 후 처리 이벤트 처리기를 포함 합니다. 이벤트 중 하나는 핸들을의 메서드 중 일부를 재정의할 수 있습니다 <xref:Microsoft.VisualStudio.Text.Editor.MouseProcessorBase>합니다.  
  
###  <a name="editoroperations"></a>편집기 작업  
 편집기 작업 스크립트에 대 한 편집기 또는 다른 목적으로 상호 작용을 자동화 데 사용할 수 있습니다. 가져올 수는 <xref:Microsoft.VisualStudio.Text.Operations.IEditorOperationsFactoryService> 액세스 작업에 주어진 <xref:Microsoft.VisualStudio.Text.Editor.ITextView>합니다. 이러한 개체를 사용 하 여 선택 항목을 수정 보기를 스크롤하거나 캐럿 보기의 다른 부분을 이동 합니다.  
  
###  <a name="intellisense"></a>IntelliSense  
 IntelliSense 문 완성, 서명 도움말 (매개 변수 정보 라고도 함), 요약 정보 및 전구를 지원합니다.  
  
 문 완성 팝업 메서드 이름, XML 요소 및 기타 코딩 이나 태그 요소에 대 한 잠재적인 완성 목록을 제공합니다. 일반적으로 사용자 제스처는 완성 세션을 호출합니다. 세션 잠재적인 완성 목록을 표시 하 고 사용자 수 하나를 선택 하거나 목록을 해제 합니다. <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionBroker> 는 만들기를 트리거하는 <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSession>합니다. <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource> 계산의 <xref:Microsoft.VisualStudio.Language.Intellisense.CompletionSet> 세션에 대 한 완성 항목의 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)   
 [편집기 가져오기](../extensibility/editor-imports.md)