---
title: "편집기의 내부를 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 새-아키텍처"
ms.assetid: 822cbb8d-7ab4-40ee-bd12-44016ebcce81
caps.latest.revision: 31
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 31
---
# 편집기의 내부를
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

편집기는 다양 한 텍스트 뷰 및 사용자 인터페이스에서 모델 별도 텍스트 편집기를 유지 하도록 설계 된 다른 하위 시스템의 구성 됩니다.  
  
 이 단원에서는 편집기의 다양 한 측면을 설명 합니다.  
  
-   [하위 시스템의 개요](../extensibility/inside-the-editor.md#overview)  
  
-   [텍스트 모델](../extensibility/inside-the-editor.md#textmodel)  
  
-   [텍스트 보기](../extensibility/inside-the-editor.md#textview)  
  
 이 섹션에서는 편집기의 기능에 설명 합니다.  
  
-   [태그 및 분류자](../extensibility/inside-the-editor.md#tagsandclassifiers)  
  
-   [도구 영역](../extensibility/inside-the-editor.md#adornments)  
  
-   [프로젝션](../extensibility/inside-the-editor.md#projection)  
  
-   [개요](../extensibility/inside-the-editor.md#outlining)  
  
-   [마우스 바인딩](../extensibility/inside-the-editor.md#mousebindings)  
  
-   [편집기 작업](../extensibility/inside-the-editor.md#editoroperations)  
  
-   [IntelliSense](../extensibility/inside-the-editor.md#intellisense)  
  
##  <a name="overview"></a> 하위 시스템의 개요  
  
### 텍스트 모델 하위 시스템  
 텍스트 모델 하위 시스템은 텍스트를 표현 하 고 해당 조작을 사용 하도록 설정 하는 일을 담당 합니다. 텍스트 모델 하위 시스템 포함는 <xref:Microsoft.VisualStudio.Text.ITextBuffer> 편집기에 표시 되는 문자 시퀀스를 설명 하는 인터페이스입니다. 이 텍스트 수정, 추적 및 여러 가지 방법으로 조작할 수 있습니다. 텍스트 모델에는 다음과 같은 측면에 대 한 형식을 제공합니다.  
  
-   텍스트 파일을 연결 하 고 읽기 및 쓰기 파일 시스템에서 관리 하는 서비스입니다.  
  
-   개체의 두 시퀀스 간의 최소한의 차이점을 발견 하는 차이점 보관용 서비스입니다.  
  
-   다른 버퍼에 있는 텍스트의 하위 집합 측면에서 버퍼에 있는 텍스트를 설명 하는 데 사용 되는 시스템입니다.  
  
 텍스트 모델 하위 시스템은 무료 사용자 인터페이스 \(UI\) 개념입니다. 예를 들어 텍스트 서식 지정 또는 텍스트 레이아웃에 책임이 없을 있고 텍스트와 연결할 수 있는 시각적 도구 영역에 대 한 정보가 없습니다.  
  
 텍스트 모델 하위 시스템의 public 형식은.NET Framework 기본 클래스 라이브러리와는 프레임 워크 MEF \(Managed Extensibility\)에 따라서만 결정 Microsoft.VisualStudio.Text.Data.dll 및 Microsoft.VisualStudio.CoreUtilitiy.dll에 포함 됩니다.  
  
### 텍스트 보기 하위 시스템  
 텍스트 보기 하위 시스템은 서식 및 텍스트를 표시 하는 일을 담당 합니다. 이 하위 시스템의 형식은 형식에 Windows Presentation Foundation \(WPF\)를 사용 하는 여부에 따라 두 계층으로 나뉩니다. 가장 중요 한 형식은 <xref:Microsoft.VisualStudio.Text.Editor.ITextView> 및 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView>, 집합을 표시 하도록 텍스트 줄의 캐럿, 선택 영역을 및 WPF UI 요소를 사용 하 여 텍스트를 표시 하기 위한 기능을 제어 하 합니다. 이 하위 시스템 제공 텍스트 주위의 여백 영역을 표시 합니다. 이러한 여백, 확장할 수 있으며 다양 한 종류의 콘텐츠 및 시각적 효과 포함할 수 있습니다. 여백에 줄 번호 표시 및 스크롤 막대는 있습니다.  
  
 텍스트 보기 하위 시스템의 public 형식 Microsoft.VisualStudio.Text.UI.dll 및 Microsoft.VisualStudio.Text.UI.Wpf.dll에 포함 됩니다. 첫 번째는 플랫폼 독립적인 요소를 포함 하 고 두 번째 WPF 관련 요소를 포함 합니다.  
  
### 분류 하위 시스템  
 분류 하위 시스템은 텍스트의 글꼴 속성을 결정 합니다. "키워드" 또는 "주석" 예를 들어 서로 다른 클래스에는 텍스트를 분리 하는 분류자입니다. 분류 서식 맵 관련이 이러한 클래스 실제 글꼴 속성을 예를 들어 "Blue 굴림 10pt"입니다. 이 정보는 포맷 하 고 텍스트를 렌더링 하는 경우 텍스트 보기에서 사용 됩니다. 태그, 텍스트의 범위와 연결 되도록 데이터를 사용 하면이 항목의 뒷부분에 자세히 설명 되어 있습니다.  
  
 분류 하위 시스템의 공용 유형이 Microsoft.VisualStudio.Text.Logic.dll에 포함 되어 및 이러한 Microsoft.VisualStudio.Text.UI.Wpf.dll에 포함 된 분류의 시각적 측면 상호 작용 합니다.  
  
### 작업 하위 시스템  
 작업 하위 시스템 편집기 동작을 정의합니다. 실행 취소 시스템 및 Visual Studio 편집기 명령에 대 한 구현을 제공합니다.  
  
## 텍스트 모델 및 텍스트 보기 자세히 보기  
  
###  <a name="textmodel"></a> 텍스트 모델  
 텍스트 모델 하위 시스템의 텍스트 형식 다른 그룹으로 구성 됩니다. 여기에 텍스트 버퍼, 텍스트 스냅숏 및 텍스트 범위가 포함 됩니다.  
  
#### 텍스트 버퍼와 텍스트 스냅숏  
 <xref:Microsoft.VisualStudio.Text.ITextBuffer> 인터페이스는 인코딩을 사용 하 여 u t F\-16을 사용 하 여 인코딩된 유니코드 문자 시퀀스로 나타냅니다는 `String` .NET Framework의 형식입니다. 파일 시스템 문서로 텍스트 버퍼를 유지할 수 있지만 그럴 필요는 없습니다.  
  
 <xref:Microsoft.VisualStudio.Text.ITextBufferFactoryService> 는 빈 텍스트 버퍼 또는 또는 문자열에서 초기화 되는 텍스트 버퍼를 만드는 데 <xref:System.IO.TextReader>합니다. 텍스트 버퍼를 파일 시스템에 유지할 수는 <xref:Microsoft.VisualStudio.Text.ITextDocument>합니다.  
  
 스레드를 호출 하 여 텍스트 버퍼의 소유권을 갖습니다 될 때까지 스레드 버퍼씩 텍스트를 편집할 수 있습니다 <xref:Microsoft.VisualStudio.Text.ITextBuffer.TakeThreadOwnership%2A>합니다. 그런 다음 해당 스레드만 편집을 수행할 수 있습니다.  
  
 텍스트 버퍼 수명 동안 여러 버전을 통해 이동할 수 있습니다. 새 버전 생성 될 때마다 버퍼를 편집 하 고 변경할 수 없는 프로그램 <xref:Microsoft.VisualStudio.Text.ITextSnapshot> 버퍼의 해당 버전의 내용을 나타냅니다. 텍스트 스냅숏을 변경이 불가능 하므로 나타내는 텍스트 버퍼 계속 변경 하는 경우에 텍스트 스냅숏을 제한 없이 모든 스레드에서 액세스할 수 있습니다.  
  
#### 텍스트 스냅숏 및 스냅숏 줄 텍스트  
 문자 시퀀스 또는 줄의 시퀀스로 텍스트 스냅숏의 내용을 볼 수 있습니다. 줄 수 있으며 모두 인덱스 0부터 시작 합니다. 빈 텍스트 스냅숏 0 문자와 한 빈 줄에 포함 됩니다. 유효한 유니코드 줄 바꿈 문자 시퀀스, 사용자나 시작 또는 버퍼의 끝 줄을 구분 합니다. 줄 바꿈 문자가 텍스트 스냅숏에서 명시적으로 표현 되 고 텍스트 스냅숏의 줄 바꿈 일부만 필요가 동일.  
  
> [!NOTE]
>  Visual Studio 편집기에서 줄 바꿈 문자에 대 한 자세한 내용은 참조 [인코딩 및 줄 바꿈](../ide/encodings-and-line-breaks.md)합니다.  
  
 텍스트 줄을 나타내는 <xref:Microsoft.VisualStudio.Text.ITextSnapshotLine> 개체를 특정 문자 위치 또는 특정 줄 번호에 대 한 텍스트 스냅숏을 얻을 수 있습니다.  
  
#### SnapshotPoints, SnapshotSpans, 및 NormalizedSnapshotSpanCollections  
 A <xref:Microsoft.VisualStudio.Text.SnapshotPoint> 스냅숏으로의 문자 위치를 나타냅니다. 위치는 0과 스냅숏의 길이 하도록 보장 됩니다. A <xref:Microsoft.VisualStudio.Text.SnapshotSpan> 스냅숏에 있는 텍스트의 범위를 나타냅니다. 끝 위치는 0과 스냅숏의 길이 하도록 보장 됩니다.<xref:Microsoft.VisualStudio.Text.NormalizedSnapshotSpanCollection> 집합으로 구성 됩니다 <xref:Microsoft.VisualStudio.Text.SnapshotSpan> 동일한 스냅숏에서 개체입니다.  
  
#### 범위 및 NormalizedSpanCollections  
 A <xref:Microsoft.VisualStudio.Text.Span> 텍스트 스냅숏 텍스트의 범위에 적용할 수 있는 간격을 나타냅니다. 범위는 0을 포함 하 여 모든 위치에서 시작할 수 있도록 스냅숏 위치는 0부터 시작 합니다.`End` 범위 속성은의 합계에 해당 `Start` 속성 및 해당 `Length` 속성입니다. A `Span` 로 인덱싱된 문자를 포함 하지 않는 `End` 속성입니다. 가 시작 하는 범위 예를 들어 5와 길이 \= \= 3에 끝이 \= 8, 5, 6 및 7 위치에 있는 문자를 포함 하 고 있습니다. 이 범위에 대 한 표기법은 5..8\) 합니다.  
  
 두 범위에 있는 경우 모든 위치에서 공통적으로 끝 위치를 포함 하 여 교차 합니다. 따라서 교차 \[3, 5\) 및 \[2, 7\)는 \[3, 5\)의 교차 및 \[3, 5\) 및 \[5, 7\)는 \[5, 5\). \(다음에 유의 \[5, 5\)는 빈 범위는.\)  
  
 두 범위에 있는 경우 위치에서 공통적으로 끝 위치를 제외 하 고 겹칩니다. 빈 범위는 다른 범위를 겹치는 되지 하 고 두 범위가 겹치는 비어 있을 수 있습니다.  
  
 A <xref:Microsoft.VisualStudio.Text.NormalizedSpanCollection> 은 해당 범위의 시작 속성 순서 대로 범위 목록입니다. 목록에서 중복 되거나 인접 범위 병합 됩니다. 예를 들어 범위 집합 \[5..9\), \[0..1\), \[3..6\), 및 \[9..10\), 정규화 된 목록은 범위 \[0..1\), \[3..10\) 합니다.  
  
#### ITextEdit, TextVersion 및 텍스트 변경 알림  
 사용 하 여 텍스트 버퍼의 콘텐츠를 변경할 수는 <xref:Microsoft.VisualStudio.Text.ITextEdit> 개체입니다. 이러한 개체를 만드는 \(중 하나를 사용 하 여는 `CreateEdit()` 방식의 <xref:Microsoft.VisualStudio.Text.ITextBuffer>\)의 텍스트 편집 구성 된 텍스트 트랜잭션을 시작 합니다. 모든 편집은 일부 문자열 버퍼의 텍스트 범위를 대체 합니다. 트랜잭션이 시작 되었을 때 좌표와의 모든 편집 내용을 버퍼의 스냅숏을 기준으로 표시 됩니다.<xref:Microsoft.VisualStudio.Text.ITextEdit> 개체가 동일한 트랜잭션 내에서 다른 편집의 영향을 받는 편집의 좌표를 조정 합니다.  
  
 예를 들어,이 문자열을 포함 하는 텍스트 버퍼를 살펴봅니다.  
  
```  
abcdefghij  
```  
  
 두 개의 편집에 범위를 대체 하는 하나의 편집을 포함 하는 트랜잭션이 적용 \[2..4\) 문자를 사용 하 여 `X` 에서 범위를 대체 하는 두 번째 편집 \[6..9\) 문자를 사용 하 여 `Y`합니다. 결과이 버퍼.  
  
```  
abXefYj  
```  
  
 두 번째 편집에 대 한 좌표 첫 번째 편집 적용 하기 전에 트랜잭션의 시작 부분에는 버퍼의 내용에 대해 계산 된 것입니다.  
  
 버퍼에 변경 내용을 적용 하면는 <xref:Microsoft.VisualStudio.Text.ITextEdit> 개체를 호출 하 여 커밋합니다 해당 `Apply()` 메서드. 하나 이상의 비어 있지 않은 편집, 발생 한 경우 새 <xref:Microsoft.VisualStudio.Text.ITextVersion> 만들어지면 새 <xref:Microsoft.VisualStudio.Text.ITextSnapshot> 만들어지면 하나의 `Changed` 이벤트가 발생 합니다. 모든 텍스트 버전이 서로 다른 텍스트 스냅숏입니다. 텍스트 스냅숏 후 편집 트랜잭션이 텍스트 버퍼의 전체 상태 나타내지만 텍스트 버전에서에서 변경 된 사항만 스냅숏 하나 다음에 대해 설명 합니다. 일반적으로 텍스트 스냅숏은 한 번 사용 및 텍스트 버전 일정 시간 동안 활성 상태로 유지 해야 하는 동안 다음 삭제 합니다.  
  
 텍스트 버전을 포함 한 <xref:Microsoft.VisualStudio.Text.INormalizedTextChangeCollection>합니다. 이 컬렉션의 변경 내용을 설명 하는, 스냅숏을 적용 하는 경우 후속 스냅숏을 생성 합니다. 모든 <xref:Microsoft.VisualStudio.Text.ITextChange> 컬렉션의 변경, 대체 문자열 및 대체 문자열의 문자 위치를 포함 합니다. 바꾼된 문자열 기본 삽입을 위해 비어 있으며 기본 삭제에 대 한 대체 문자열이 비어 있습니다. 정규화 된 컬렉션은 항상 `null` 텍스트 버퍼의 가장 최신 버전에 대 한 합니다.  
  
 하나의 <xref:Microsoft.VisualStudio.Text.ITextEdit> 언제 든 지 텍스트 버퍼에 대 한 개체를 인스턴스화할 수 및 모든 텍스트 편집 \(소유권을 요구 한\) 경우 텍스트 버퍼를 소유 하는 스레드에서 수행 되어야 합니다. 호출 하 여 텍스트 편집을 중단 될 수는 `Cancel` 메서드 또는 해당 `Dispose` 메서드.  
  
 <xref:Microsoft.VisualStudio.Text.ITextBuffer> 또한 제공 `Insert()`, `Delete()`, 및 `Replace()` 에 비슷한 메서드를 찾을 <xref:Microsoft.VisualStudio.Text.ITextEdit> 인터페이스입니다. 이러한 호출 된 것과 동일한 효과가 만들기는 <xref:Microsoft.VisualStudio.Text.ITextEdit> 개체는 비슷한 호출을 실행 한 다음 편집을 적용 합니다.  
  
#### 추적 지점 및 추적 범위  
 <xref:Microsoft.VisualStudio.Text.ITrackingPoint> 텍스트 버퍼의 문자 위치를 나타냅니다. 바꾸려는 문자의 위치 하는 방법으로, 버퍼를 편집한 경우와 추적 지점으로 이동 합니다. 예를 들어 추적 지점은 버퍼에 10 위치를 참조 하는 경우 5 개 문자 버퍼의 시작 부분에 삽입 됩니다 추적 지점은 다음 위치를 나타냅니다 15. 해당 동작은에 의해 결정 됩니다 정확 하 게 추적 지점을 가리키는 위치에 삽입 되 면 해당 <xref:Microsoft.VisualStudio.Text.PointTrackingMode>, 될 수 있습니다 `Positive` 또는 `Negative`합니다. 삽입;의 끝에는 이제 된 같은 문자를 추적 지점에서 참조 된 추적 모드 양수 이면 추적 모드를 사용 하는 음수 이면 추적 지점의 원래 위치에 삽입 된 첫 번째 문자를 가리킵니다. 추적 지점을 나타내는 위치에 있는 문자가 삭제 되 면 삭제 된 범위를 뒤에 오는 첫 번째 문자는 추적 지점을 이동 합니다. 예를 들어 추적 지점 위치 5에 있는 문자가 나타내며 3 ~ 6 위치에 문자가 삭제, 추적 지점을 3 위치의 문자를 참조 합니다.  
  
 <xref:Microsoft.VisualStudio.Text.ITrackingSpan> 하나만 위치가 아닌 문자 범위를 나타냅니다. 해당 동작은 의해 결정 되는 <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>합니다. 범위 추적 모드를 사용 하는 경우 <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, 범위 추적 모드를 사용 하는 경우의 가장자리;에 삽입 하는 텍스트를 통합 하기 위해 추적 범위 증가 <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, 추적 범위 가장자리에 삽입 하는 텍스트를 포함 되지 않습니다. 그러나 범위 추적 모드를 사용 하는 경우 <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, 삽입, 처음으로 현재 위치를 푸시 경우 범위 추적 모드 <xref:Microsoft.VisualStudio.Text.SpanTrackingMode>, 삽입 끝으로 현재 위치를 푸시합니다.  
  
 소속 된 텍스트 버퍼의 모든 스냅숏에 대 한 추적 지점의 위치 또는 추적 범위의 범위를 가져올 수 있습니다. 추적 지점 및 추적 범위 모든 스레드에서 안전 하 게 참조할 수 있습니다.  
  
#### 콘텐츠 형식  
 콘텐츠 형식은 여러 종류의 콘텐츠를 정의 하기 위한 메커니즘입니다. 콘텐츠 형식을 파일 형식 예: "text", "code" 또는 "binary" 또는 "xml", "vb" 또는 "c\#"과 같은 기술 형식 수 있습니다. 예를 들어 키워드 다른 프로그래밍 언어에 없지만 C\# 및 Visual Basic의 경우에 단어 "using"입니다. 따라서이 키워드의 정의 "c\#" 및 "vb" 콘텐츠 형식 제한 됩니다.  
  
 콘텐츠 형식은 장식 및 편집기의 다른 요소에 대 한 필터로 사용 됩니다. 콘텐츠 형식별; 정의 된 다양 한 편집기 기능 및 확장 지점 예를 들어 텍스트 색은 일반 텍스트 파일, XML 파일 및 Visual Basic 소스 코드 파일에 대 한 다릅니다. 텍스트 버퍼 일반적으로 연결 된 콘텐츠 형식은 생성 되 고 텍스트 버퍼의 콘텐츠 형식을 변경할 수 있습니다.  
  
 콘텐츠 형식은 여러\-에서 상속할 수 다른 콘텐츠 형식을.<xref:Microsoft.VisualStudio.Utilities.ContentTypeDefinition> 지정 된 콘텐츠 형식의 부모 항목을 여러 기본 형식을 지정할 수 있습니다.  
  
 개발자 자신의 콘텐츠 형식을 정의 업데이트 하 고 사용 하 여 등록할 수는 <xref:Microsoft.VisualStudio.Utilities.IContentTypeRegistryService>합니다. 사용 하 여 특정 콘텐츠 형식에 대해 다양 한 편집기 기능을 정의할 수 있습니다는 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>합니다. 예를 들어, 편집기, 장식, 여백과 마우스 처리기 정의할 수 있습니다 특정 콘텐츠 형식을 표시 하는 편집기에만 적용 되도록 합니다.  
  
###  <a name="textview"></a> 텍스트 보기  
 모델 뷰 컨트롤러 \(MVC\) 패턴의 보기 파트 텍스트 뷰, 뷰, 스크롤 막대와 같은 그래픽 요소 서식을 정의 합니다. Visual Studio 편집기의 모든 프레젠테이션 요소는 WPF를 기반으로 합니다.  
  
#### 텍스트 뷰  
 <xref:Microsoft.VisualStudio.Text.Editor.ITextView> 인터페이스는 텍스트 뷰는 플랫폼에 관계 없이 나타냅니다. 텍스트 문서 창에 표시 하는 데 주로 사용 되는 하지만 사용할 수 있습니다도 다른 용도로 예를 들어 도구 설명에.  
  
 텍스트 뷰는 다양 한 종류의 텍스트 버퍼를 참조합니다.<xref:Microsoft.VisualStudio.Text.Editor.ITextView.TextViewModel%2A> 속성은 참조는 <xref:Microsoft.VisualStudio.Text.Editor.ITextViewModel> 이러한 세 개의 다른 텍스트 버퍼를 가리키는 개체: 발생는 편집 및 텍스트 보기에 표시 되는 버퍼는 시각적 버퍼에서 편집 버퍼를 최상위 수준 데이터 버퍼는 데이터 버퍼입니다.  
  
 텍스트 내부 텍스트 버퍼에 연결 하는 분류자에 따라 서식이 지정 되어 있고 텍스트 뷰 자체에 연결 되어 있는 장식 공급자를 사용 하 여 표시 됩니다.  
  
#### 텍스트 뷰 좌표계  
 텍스트 뷰 좌표계 텍스트 보기에는 위치를 지정합니다. 이 좌표 시스템의 x 표시 되 고 텍스트의 왼쪽된 가장자리에 해당 하는 값 0.0 및 y 값 0.0은 표시 되는 텍스트의 위쪽 가장자리에 해당 합니다. x 왼쪽에서 오른쪽으로 증가 조정 및 y 증가 위쪽에서 아래쪽으로 조정 합니다.  
  
 뷰포트 \(텍스트 창에 표시 되는 텍스트의 일부\) 가로로 스크롤할 수 같은 방식으로 세로로 스크롤 된 합니다. 뷰포트 그리기 화면을 기준으로 이동 하는 왼쪽된 좌표를 변경 하 여 가로 방향으로 스크롤됩니다. 그러나 뷰포트 스크롤할 수 있는 세로 방향으로 발생 하는 렌더링 된 텍스트를 변경한 경우에 한 <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> 이벤트를 발생 합니다.  
  
 좌표계에서 거리가 논리 픽셀에 해당합니다. 텍스트 렌더링 화면과 배율 변환 없이 표시 되 면 하나의 단위로 텍스트 렌더링 좌표계 디스플레이에 하나의 픽셀에 해당 합니다.  
  
#### 여백  
 <xref:Microsoft.VisualStudio.Text.Editor.ITextViewMargin> 인터페이스는 여백을 나타내는 및 여백 및 크기의 표시 방식 제어를 사용 합니다. "Top", "왼쪽", "오른쪽" 및 "아래" 라고 하며 위쪽, 아래쪽, 왼쪽 또는 보기의 오른쪽 가장자리에 연결 되어 있는 미리 정의 된 여백 네 가지가 있습니다. 이러한 여백은 컨테이너 다른 여백과 배치할 수 있습니다. 인터페이스는 여백 크기와 여백의 표시 여부를 반환 하는 메서드를 정의 합니다. 여백은 연결 되어 있는 텍스트 보기에 대 한 추가 정보를 제공 하는 시각적 요소입니다. 예를 들어, 줄 번호 여백 텍스트 보기에 대 한 줄 번호를 표시합니다. 문자 모양 여백 UI 요소를 표시합니다.  
  
 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewMarginProvider> 생성 및 여백의 배치를 처리 하는 인터페이스입니다. 여백이 다른 여백과 관련 하 여 주문할 수 있습니다. 우선 순위가 높은 여백은 텍스트 보기에 가깝게 위치입니다. 예를 들어 경우에 두 개의 왼쪽된 여백, 여백 A 및 B, 여백 및 여백을 B가 A 여백 보다 낮은 우선 순위, 여백 B 나타납니다 왼쪽의 여백 1.  
  
#### 텍스트 뷰 호스트  
 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> 텍스트 뷰 및 예를 들어 한 스크롤 막대의 보기와 함께 제공 되는 모든 인접 장식을 인터페이스를 포함 합니다. 텍스트 뷰 호스트 보기의 테두리에 연결 되어 있는 여백이 포함 됩니다.  
  
#### 서식 있는 텍스트  
 텍스트 보기에 표시 되는 텍스트는 이루어져 <xref:Microsoft.VisualStudio.Text.Formatting.ITextViewLine> 개체입니다. 모든 텍스트 뷰 줄 텍스트 보기에는 텍스트 한 줄에 해당합니다. 긴 줄으로 내부 버퍼의 수 수 부분적으로 가려진 \(줄 바꿈 사용 하지 않는\) 하는 경우 또는 여러 텍스트 뷰 줄으로 나뉘어집니다.<xref:Microsoft.VisualStudio.Text.Formatting.ITextViewLine> 인터페이스 메서드 및 좌표와 문자 간의 매핑에 대 한 한 줄으로 연결할 수 있는 도구 영역에 대 한 속성을 포함 합니다.  
  
 <xref:Microsoft.VisualStudio.Text.Formatting.ITextViewLine> 개체를 사용 하 여 생성 되는 <xref:Microsoft.VisualStudio.Text.Formatting.IFormattedLineSource> 인터페이스입니다. 현재 보기에 표시 되는 텍스트에만 관심이, 서식의 원본을 무시할 수 있습니다. 없는 텍스트의 서식을에 관심이 있는 경우 \(예: 서식 있는 텍스트 잘라내기 지원 하 여 붙여 넣는\), 보기에 표시 된 사용할 수 있습니다 <xref:Microsoft.VisualStudio.Text.Formatting.IFormattedLineSource> 텍스트 버퍼의 텍스트 서식을 지정 하려면.  
  
 텍스트 뷰 형식 하나 <xref:Microsoft.VisualStudio.Text.ITextSnapshotLine> 한 번에 있습니다.  
  
## 편집기 기능  
 편집기의 기능 기능의 정의 별도의 구현 하도록 설계 됩니다. 편집기에는 이러한 기능이 포함 됩니다.  
  
-   태그 및 분류자  
  
-   도구 영역  
  
-   프로젝션  
  
-   개요  
  
-   마우스와 키 바인딩  
  
-   작업 및 기본 형식  
  
-   IntelliSense  
  
###  <a name="tagsandclassifiers"></a> 태그 및 분류자  
 태그는 텍스트의 범위와 연관 된 표식입니다. 이러한에 제공할 수 다양 한 방법으로 예를 들어 텍스트 색, 밑줄, 그래픽 또는 팝업을 사용 하 여 합니다. 분류자는 태그의 한 종류입니다.  
  
 다른 종류의 태그는 <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag> 텍스트에 강조 표시에 대 한 <xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag> 개요에 대 한 및 <xref:Microsoft.VisualStudio.Text.Tagging.ErrorTag> 컴파일 오류입니다.  
  
#### 분류 형식  
 <xref:Microsoft.VisualStudio.Text.Classification.IClassificationType> 인터페이스는 텍스트의 경우 추상 범주는 동급 클래스를 나타냅니다. 분류 형식 수 다중\-형식에서 상속 다른 분류 합니다. 예를 들어, 프로그래밍 언어 분류 포함 될 수 있습니다 "키워드", "설명" 및 "식별자"는 모두 "code"에서 상속 합니다. 자연 언어 분류 형식 "명사", "동사" 및 "형용사" 모두에서 상속 하는 "자연 언어"를 포함할 수 있습니다.  
  
#### 분류  
 분류는 텍스트의 범위를 통해 일반적으로 특정 분류 형식의 인스턴스입니다. A <xref:Microsoft.VisualStudio.Text.Classification.ClassificationSpan> 분류를 나타내는 데 사용 됩니다. 분류 범위를 텍스트의 특정 범위에 설명 하 고이 텍스트 범위는 특정 분류 형식 시스템에 지시 하는 레이블을으로 생각할 수 있습니다.  
  
#### 분류자  
 <xref:Microsoft.VisualStudio.Text.Classification.IClassifier> 는 텍스트 분류의 집합으로 분리 하는 메커니즘입니다. 분류자 특정 콘텐츠 형식에 대해 정의 하 고 특정 텍스트 버퍼에 대해 인스턴스화된 해야 합니다. 클라이언트를 구현 해야 <xref:Microsoft.VisualStudio.Text.Classification.IClassifier> 텍스트 분류에 참여할 수 있습니다.  
  
#### 분류자 집계  
 분류자 집계는 분류를 하나의 집합으로 하나의 텍스트 버퍼에 대 한 모든 분류자를 결합 하는 메커니즘입니다. 예를 들어, C\# 분류자와 영어 분류자 수 C\# 파일에 주석을 통해 분류를 만듭니다. 이 주석은 고려해 야 합니다.  
  
```  
// This method produces a classifier  
```  
  
 C\# 분류자 수을 주석으로 전체 범위 레이블과 영어 분류자 수 "생성"로 분류할 "동사" 및 "method"는 "명사"로 합니다. 수집기 겹치지 않는 분류의 집합을 생성 하 고 집합의 유형은 모든 기 고물에 따라 키를 누릅니다.  
  
 분류자 집계를 분류 집합에 텍스트를 분리 하기 때문에 분류자 이기도 합니다. 분류자 집계 갖는지도 확인 겹치는 사용할 수 있는 분류 하 고 분류 정렬 됩니다. 개별 분류자 분류, 집합 순서에 관계 없이 반환 되며 어떤 식으로든에서 겹치는 됩니다.  
  
#### 분류 서식 및 텍스트 색  
 텍스트 서식 지정은 예는 텍스트 분류를 기반으로 하는 기능입니다. 응용 프로그램에서 텍스트 표시를 확인 하려면 텍스트 뷰 계층에서 사용 됩니다. 텍스트 서식 지정 영역 WPF에 종속 되어 있지만 분류의 논리 정의 되지 않습니다.  
  
 분류 형식은 서식 특정 분류 유형에 대 한 속성 집합입니다. 이러한 형식에서 분류 유형의 부모 형식에서 상속합니다.  
  
 <xref:Microsoft.VisualStudio.Text.Classification.IClassificationFormatMap> 텍스트 서식 속성 집합에는 분류 형식에서 맵입니다. 편집기에서 서식 맵 구현의 분류 형식의 모든 내보내기를 처리합니다.  
  
###  <a name="adornments"></a> 도구 영역  
 장식을 직접 관련이 없는 글꼴 및 색의 텍스트 보기에 문자를 그래픽 효과입니다. 예를 들어, 다양 한 프로그래밍 언어에 대 한 비 컴파일 코드를 표시 하는 데 사용 되는 빨간색 물결선 밑줄은 포함 된 adornment 되며 도구 설명에 팝업 도구 영역. 도구 영역에서 파생 된 <xref:System.Windows.UIElement> 구현 및 <xref:Microsoft.VisualStudio.Text.Tagging.ITag>합니다. 두 가지 특수 한 유형의 장식 태그를는 <xref:Microsoft.VisualStudio.Text.Tagging.SpaceNegotiatingAdornmentTag>, 뷰의 텍스트와 같은 공간을 차지 하는 도구 영역에 대 한 고 <xref:Microsoft.VisualStudio.Text.Tagging.ErrorTag>, 물결선 밑줄에 대 한 합니다.  
  
 포함 된 장식을 서식 있는 텍스트 보기의 일부를 구성 하는 그래픽입니다. 다른 z 레이어에 구성 됩니다. 다음과 같이 세 가지 기본 제공 계층 가지 있습니다: 텍스트, 캐럿 및 선택 합니다. 그러나 개발자 레이어를 정의 하 고 다른 순서로 배치할 수 있습니다. 장식 포함 된 세 가지는 상대 텍스트 장식 \(함 텍스트 이동 하면 이동 하 고는 텍스트를 삭제 해도 삭제\), \(보기의 비 텍스트 부분을 사용 하 여 수행할 필요\)는 보기에 상대적인 장식 및 소유자 제어 장식 \(개발자의 위치를 관리 해야\) 합니다.  
  
 팝업 장식을 예를 들어 도구 설명 텍스트 보기, 위에 작은 창에 표시 되는 그래픽입니다.  
  
###  <a name="projection"></a> 프로젝션  
 프로젝션은 다른 종류의 텍스트를 실제로 저장 하지 않으므로 하지만 다른 텍스트 버퍼에서 텍스트를 결합 하는 대신 텍스트 버퍼를 생성 하기 위한 기술입니다. 예를 들어 다른 두 개의 버퍼에서 텍스트를 연결 하 고 하나의 버퍼에 말 이죠 결과 표시 하거나 하나의 버퍼에서 텍스트의 부분을 숨기려면에 프로젝션 버퍼를 사용할 수 있습니다. 프로젝션 버퍼 다른 프로젝션 버퍼를 소스 버퍼도 작동할 수 있습니다. 다양 한 방법으로 텍스트를 다시 정렬 하려면 프로젝션에 관련 된 버퍼 집합을 생성할 수 있습니다. \(이러한 집합은 라고도 *버퍼 그래프*.\) Visual Studio 텍스트 윤곽선 지정 기능이 축소 된 텍스트를 숨기려면 프로젝션 버퍼를 사용 하 여 구현 되 고 Visual Basic 및 C\#과 같은 포함 된 언어를 지원 하기 위해 도법을 사용 하는 ASP.NET 페이지에 대 한 Visual Studio 편집기.  
  
 <xref:Microsoft.VisualStudio.Text.Projection.IProjectionBuffer> 사용 하 여 만든 <xref:Microsoft.VisualStudio.Text.Projection.IProjectionBufferFactoryService>합니다. 정렬된 된 시퀀스를 나타내는 프로젝션 버퍼 <xref:Microsoft.VisualStudio.Text.ITrackingSpan> 이라고 하는 개체 *소스 범위*합니다. 이러한 범위의 내용은 일련의 문자로 표시 됩니다. 소스 범위 그려집니다 텍스트 버퍼 라고 *소스 버퍼*합니다. 프로젝션 버퍼의 클라이언트는 일반 텍스트 버퍼에서가 다른 것을 알아야 할 필요가 없습니다.  
  
 프로젝션 버퍼 소스 버퍼에 텍스트 변경 이벤트를 수신합니다. 원본에서 텍스트 범위의 변경 내용을 프로젝션 버퍼 자체 좌표로 변경 된 텍스트 좌표를 매핑하고 적절 한 텍스트 변경 이벤트를 발생 시킵니다. 예를 들어 이러한 내용이 들어 있는 소스 버퍼를 A와 B는 것이 좋습니다.  
  
```  
A: ABCDE  
B: vwxyz  
```  
  
 프로젝션 버퍼 P 하나 모든 버퍼 A, B, 버퍼의 모두가지고 있는 다른 두 개의 텍스트 범위에서 형성 됩니다 P에는 다음 내용이 있습니다.  
  
```  
P: ABCDEvwxyz  
```  
  
 경우 부분 문자열 `xy` 버퍼 P 7과 8 위치에 문자가 삭제 된 나타내는 이벤트를 발생 시킵니다 B, 버퍼에서 삭제 됩니다.  
  
 프로젝션 버퍼를 직접 편집할 수도 있습니다. 적절 한 소스 버퍼에 대 한 편집을 전파합니다. 예를 들어 문자열이 위치 6 \(문자 "v"의 원래 위치\)에서 P 버퍼에 삽입, 삽입 위치 1에서 B 버퍼에 전파 됩니다.  
  
 프로젝션 버퍼에 기여 하는 소스 범위에 대 한 제한 사항이 있습니다. 소스 범위와 겹치지 않을 수 있습니다. 프로젝션 버퍼의 위치는 모든 소스 버퍼에서 둘 이상의 위치에 매핑할 수 없습니다 및 소스 버퍼의 위치는 프로젝션 버퍼에서 둘 이상의 위치에 매핑할 수 없습니다. 소스 버퍼 관계 없는 circularities 허용 됩니다.  
  
 이벤트 소스의 집합 버퍼링 프로젝션 버퍼 변경 하 고 변경 내용을 원본 집합에 걸쳐 있는 경우 발생 합니다.  
  
 생략 버퍼는 프로젝션 버퍼의 특수 한 종류입니다. 개요에 대 한 확장 및 텍스트 블록을 축소 하는 작업에 주로 사용 됩니다. 생략 버퍼 하나의 소스 버퍼를 기반으로 하며 생략 버퍼에서 범위 대로 정렬 되어야 합니다 동일한 소스 버퍼의 순서 대로 수행 됩니다.  
  
##### 버퍼 그래프  
 <xref:Microsoft.VisualStudio.Text.Projection.IBufferGraph> 프로젝션 버퍼에 대 한 그래프에서 인터페이스에 매핑할 수 있도록 합니다. 모든 텍스트 버퍼 및 프로젝션 버퍼는 방향이 있는 비순환 그래프는 언어 컴파일러에 의해 생성 되는 추상 구문 트리 비슷하게에 수집 됩니다. 그래프는 모든 텍스트 버퍼 될 수 있는 최상위 버퍼에 의해 정의 됩니다. 소스 버퍼의 지점에 상위 버퍼의 위치 또는 상위 버퍼 집합 소스 버퍼의 범위에 있는 범위에서 버퍼 그래프 매핑할 수 있습니다. 마찬가지로, 점을 매핑할 수도 있고 소스 버퍼에서 최상위 버퍼의 지점에 걸쳐 있습니다. 버퍼 그래프를 사용 하 여 생성 되는 <xref:Microsoft.VisualStudio.Text.Projection.IBufferGraphFactoryService>합니다.  
  
##### 이벤트 및 프로젝션 버퍼  
 프로젝션 버퍼를 수정한 경우 수정 작업에 종속 된 버퍼에 프로젝션 버퍼에서 전송 됩니다. 모든 버퍼가 수정 되 면 버퍼 변경 이벤트가 발생 되 면 가장 깊이 버퍼로 시작 합니다.  
  
###  <a name="outlining"></a> 개요  
 개요 확장 또는 다른 텍스트 블록을 텍스트 뷰를 축소 하는 기능입니다. 한 종류로 정의 된 개요의 <xref:Microsoft.VisualStudio.Text.Tagging.ITag>, 에서 같은 방식으로 장식 정의 됩니다. A <xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag> 확장 하거나 축소할 수 있는 텍스트 영역을 정의 하는 태그입니다. 개요를 사용 하려면 가져와야는 <xref:Microsoft.VisualStudio.Text.Outlining.IOutliningManagerService> 가져오려는 <xref:Microsoft.VisualStudio.Text.Outlining.IOutliningManager>합니다. 개요 관리자 열거를 축소 하 고 다른 블록으로 표시 되는 확장 <xref:Microsoft.VisualStudio.Text.Outlining.ICollapsible> 개체 및 그에 따라 이벤트를 발생 시킵니다.  
  
###  <a name="mousebindings"></a> 마우스 바인딩  
 마우스 바인딩에 서로 다른 명령에 마우스 움직임을 연결합니다. 마우스 바인딩을 사용 하 여 정의 <xref:Microsoft.VisualStudio.Text.Editor.IMouseProcessorProvider>, 와 키 바인딩을 사용 하 여 정의 되는 <xref:Microsoft.VisualStudio.Text.Editor.IKeyProcessorProvider>합니다.<xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> 자동으로 모든 바인딩을 인스턴스화하고 보기에서 마우스 이벤트에 연결 합니다.  
  
 <xref:Microsoft.VisualStudio.Text.Editor.IMouseProcessor> 여러 마우스 이벤트에 대 한 전처리 및 후 처리 이벤트 처리기를 포함 하는 인터페이스입니다. 이벤트 중 하나는 핸들을의 메서드 중 일부를 재정의할 수 있습니다 <xref:Microsoft.VisualStudio.Text.Editor.MouseProcessorBase>합니다.  
  
###  <a name="editoroperations"></a> 편집기 작업  
 편집기 작업 자동화 스크립트에 대 한 편집기 또는 다른 목적으로 상호 작용을 사용할 수 있습니다. 가져올 수는 <xref:Microsoft.VisualStudio.Text.Operations.IEditorOperationsFactoryService> 액세스 작업에 주어진 <xref:Microsoft.VisualStudio.Text.Editor.ITextView>합니다. 그런 다음 선택 항목을 수정, 보기를 스크롤하여 또는 보기의 다른 부분에 캐럿을 이동할 이러한 개체를 사용할 수 있습니다.  
  
###  <a name="intellisense"></a> IntelliSense  
 IntelliSense 문 완성, 서명 도움말 \(매개 변수 정보 라고도 함\), 요약 정보 및 전구를 지원합니다.  
  
 문 완성 팝업 목록이 메서드 이름, XML 요소 및 기타 코딩 이나 태그 요소에 대 한 잠재적인 완성을 제공합니다. 일반적으로 사용자 제스처 완성 세션을 호출합니다. 세션 잠재적인 완성 목록을 표시 하 고 사용자 수 하나를 선택 하거나 목록을 해제 합니다.<xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionBroker> 는 만들기를 트리거하는 <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSession>합니다.<xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource> 계산의 <xref:Microsoft.VisualStudio.Language.Intellisense.CompletionSet> 세션에 대 한 완료 항목입니다.  
  
## 참고 항목  
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)   
 [편집기 가져오기](../extensibility/editor-imports.md)