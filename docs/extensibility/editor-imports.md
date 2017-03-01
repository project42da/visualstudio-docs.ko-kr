---
title: "편집기 가져오기 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], new - services
ms.assetid: 8d096de3-33b4-427a-a122-4aeff8a72da0
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: 2c7daddb7cd40dd0e5d24f01df141ce30ba713f9
ms.lasthandoff: 02/22/2017

---
# <a name="editor-imports"></a>편집기 가져오기
편집기 서비스, 팩터리, 및 코어 편집기에 다른 종류의 액세스에 확장을 제공 하는 브로커의 수를 가져올 수 있습니다. 예를 들어, 가져올 수는 <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>제공 하는 <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigator>지정된 된 콘텐츠 형식에 대 한.</xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigator> </xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> (이 탐색기 허용 텍스트 버퍼에서 다른 유형의 검색을 수행 합니다.)  
  
 편집기 가져오기를 사용 하려면 가져올 있습니다 필드 또는 관리 되는 확장성 프레임 워크 구성 요소 부분을 내보내는 클래스의 속성으로.  
  
> [!NOTE]
>  관리 되는 확장성 프레임 워크에 대 한 자세한 내용은 참조 [Framework MEF (Managed Extensibility)](http://msdn.microsoft.com/Library/6c61b4ec-c6df-4651-80f1-4854f8b14dde)합니다.  
  
## <a name="import-syntax"></a>가져오기 구문  
 다음 예제에서는 편집기를 가져오는 방법 옵션 팩터리 서비스를 보여 줍니다.  
  
```  
[Import]  
internal IEditorOptionsFactoryService EditorOptions { get; set; }  
```  
  
 서비스는 필드와 속성이 아니라로 가져오려는 경우 설정 해야 `null` 하지 변수에 할당 하는 방법에 대 한 컴파일러 경고를 방지 하기 위해 선언에서:  
  
```  
[Import]  
internal IEditorOptionsFactoryService m_editorOptions = null;  
```  
  
 자세한 가져오기 사용 예제를 보려면 다음 연습을 참조 합니다.  
  
 [연습: 여백 모양 만들기](../extensibility/walkthrough-creating-a-margin-glyph.md)  
  
 [연습: 텍스트 뷰를 사용자 지정](../extensibility/walkthrough-customizing-the-text-view.md)  
  
 [연습: 텍스트를 강조 표시](../extensibility/walkthrough-highlighting-text.md)  
  
 [연습: 요약 정보 도구 설명 표시](../extensibility/walkthrough-displaying-quickinfo-tooltips.md)  
  
 [연습: 서명 도움말 표시](../extensibility/walkthrough-displaying-signature-help.md)  
  
 [연습: 문 완성 표시](../extensibility/walkthrough-displaying-statement-completion.md)  
  
 [연습: 스마트 태그 표시](../misc/walkthrough-displaying-smarttags.md)  
  
## <a name="importing-the-service-provider"></a>서비스 공급자 가져오기  
 가져올 수도 있습니다는 <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider>(Microsoft.VisualStudio.Shell.Immutable.10.0 어셈블리에 있는) Visual Studio 서비스에 대 한 액세스 권한을 얻는 데 동일한 방식에서:</xref:Microsoft.VisualStudio.Shell.SVsServiceProvider>  
  
```  
[Import]  
internal SVsServiceProvider ServiceProvider = null;   
```  
  
 참조 [연습: DTE 개체에 액세스 하는 편집기 확장에서](../extensibility/walkthrough-accessing-the-dte-object-from-an-editor-extension.md) 에 대 한 자세한 내용은 합니다.  
  
## <a name="services"></a>서비스  
 편집기 서비스는 서비스를 제공 하 고 여러 구성 요소 간에 공유 되는 일반적으로 단일 엔터티.  
  
|가져오기|제공|  
|------------|--------------|  
|<xref:Microsoft.VisualStudio.Utilities.IFileExtensionRegistryService></xref:Microsoft.VisualStudio.Utilities.IFileExtensionRegistryService>|파일 확장명 간의 관계 및 <xref:Microsoft.VisualStudio.Utilities.IContentType>개체.</xref:Microsoft.VisualStudio.Utilities.IContentType>|  
|<xref:Microsoft.VisualStudio.Utilities.IContentTypeRegistryService></xref:Microsoft.VisualStudio.Utilities.IContentTypeRegistryService>|컬렉션을 <xref:Microsoft.VisualStudio.Utilities.IContentType>개체.</xref:Microsoft.VisualStudio.Utilities.IContentType>|  
|<xref:Microsoft.VisualStudio.Editor.IVsFontsAndColorsInformationService></xref:Microsoft.VisualStudio.Editor.IVsFontsAndColorsInformationService>|<xref:Microsoft.VisualStudio.Editor.IVsFontsAndColorsInformation>개체</xref:Microsoft.VisualStudio.Editor.IVsFontsAndColorsInformation>|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService></xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService>|많은 편집기 어댑터가 개체:<br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow></xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer></xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator></xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView></xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>|  
|<xref:Microsoft.VisualStudio.Text.IncrementalSearch.IIncrementalSearchFactoryService></xref:Microsoft.VisualStudio.Text.IncrementalSearch.IIncrementalSearchFactoryService>|<xref:Microsoft.VisualStudio.Text.IncrementalSearch.IIncrementalSearch>주어진된 텍스트 보기에 대 한 개체입니다.</xref:Microsoft.VisualStudio.Text.IncrementalSearch.IIncrementalSearch>|  
|<xref:Microsoft.VisualStudio.Text.ITextBufferFactoryService></xref:Microsoft.VisualStudio.Text.ITextBufferFactoryService>|An <xref:Microsoft.VisualStudio.Text.ITextBuffer>.</xref:Microsoft.VisualStudio.Text.ITextBuffer>|  
|<xref:Microsoft.VisualStudio.Text.ITextDocumentFactoryService></xref:Microsoft.VisualStudio.Text.ITextDocumentFactoryService>|An <xref:Microsoft.VisualStudio.Text.ITextDocument>.</xref:Microsoft.VisualStudio.Text.ITextDocument>|  
|<xref:Microsoft.VisualStudio.Text.Differencing.IDifferenceService></xref:Microsoft.VisualStudio.Text.Differencing.IDifferenceService>|<xref:Microsoft.VisualStudio.Text.Differencing.IDifferenceCollection%601>차이점.</xref:Microsoft.VisualStudio.Text.Differencing.IDifferenceCollection%601>|  
|<xref:Microsoft.VisualStudio.Text.Differencing.IHierarchicalStringDifferenceService></xref:Microsoft.VisualStudio.Text.Differencing.IHierarchicalStringDifferenceService>|<xref:Microsoft.VisualStudio.Text.Differencing.IHierarchicalDifferenceCollection>차이점.</xref:Microsoft.VisualStudio.Text.Differencing.IHierarchicalDifferenceCollection>|  
|<xref:Microsoft.VisualStudio.Text.Projection.IProjectionBufferFactoryService></xref:Microsoft.VisualStudio.Text.Projection.IProjectionBufferFactoryService>|<xref:Microsoft.VisualStudio.Text.Projection.IProjectionBuffer>나 <xref:Microsoft.VisualStudio.Text.Projection.IElisionBuffer>.</xref:Microsoft.VisualStudio.Text.Projection.IElisionBuffer> </xref:Microsoft.VisualStudio.Text.Projection.IProjectionBuffer>|  
|<xref:Microsoft.VisualStudio.Text.Projection.IBufferGraphFactoryService></xref:Microsoft.VisualStudio.Text.Projection.IBufferGraphFactoryService>|<xref:Microsoft.VisualStudio.Text.Projection.IBufferGraph>집합이 <xref:Microsoft.VisualStudio.Text.ITextBuffer>개체.</xref:Microsoft.VisualStudio.Text.ITextBuffer> </xref:Microsoft.VisualStudio.Text.Projection.IBufferGraph>|  
|<xref:Microsoft.VisualStudio.Text.Classification.IClassifierAggregatorService></xref:Microsoft.VisualStudio.Text.Classification.IClassifierAggregatorService>|<xref:Microsoft.VisualStudio.Text.Classification.IClassifier> <xref:Microsoft.VisualStudio.Text.ITextBuffer>.</xref:Microsoft.VisualStudio.Text.ITextBuffer> </xref:Microsoft.VisualStudio.Text.Classification.IClassifier>|  
|<xref:Microsoft.VisualStudio.Text.Classification.IViewClassifierAggregatorService></xref:Microsoft.VisualStudio.Text.Classification.IViewClassifierAggregatorService>|<xref:Microsoft.VisualStudio.Text.Classification.IClassifier> <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.</xref:Microsoft.VisualStudio.Text.Editor.ITextView> </xref:Microsoft.VisualStudio.Text.Classification.IClassifier>|  
|<xref:Microsoft.VisualStudio.Text.Classification.IClassificationFormatMapService></xref:Microsoft.VisualStudio.Text.Classification.IClassificationFormatMapService>|<xref:Microsoft.VisualStudio.Text.Classification.IClassificationFormatMap> <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.</xref:Microsoft.VisualStudio.Text.Editor.ITextView> </xref:Microsoft.VisualStudio.Text.Classification.IClassificationFormatMap>|  
|<xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMapService></xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMapService>|<xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap> <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.</xref:Microsoft.VisualStudio.Text.Editor.ITextView> </xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap>|  
|<xref:Microsoft.VisualStudio.Text.Classification.IClassificationTypeRegistryService></xref:Microsoft.VisualStudio.Text.Classification.IClassificationTypeRegistryService>|컬렉션을 유지 관리 <xref:Microsoft.VisualStudio.Text.Classification.IClassificationType>개체.</xref:Microsoft.VisualStudio.Text.Classification.IClassificationType>|  
|<xref:Microsoft.VisualStudio.Text.Tagging.IBufferTagAggregatorFactoryService></xref:Microsoft.VisualStudio.Text.Tagging.IBufferTagAggregatorFactoryService>|<xref:Microsoft.VisualStudio.Text.Tagging.ITagAggregator%601>텍스트 버퍼에 대 한.</xref:Microsoft.VisualStudio.Text.Tagging.ITagAggregator%601>|  
|<xref:Microsoft.VisualStudio.Text.Tagging.IViewTagAggregatorFactoryService></xref:Microsoft.VisualStudio.Text.Tagging.IViewTagAggregatorFactoryService>|<xref:Microsoft.VisualStudio.Text.Tagging.ITagAggregator%601>텍스트 보기에 대 한.</xref:Microsoft.VisualStudio.Text.Tagging.ITagAggregator%601>|  
|<xref:Microsoft.VisualStudio.Text.Editor.IEditorOptionsFactoryService></xref:Microsoft.VisualStudio.Text.Editor.IEditorOptionsFactoryService>|<xref:Microsoft.VisualStudio.Text.Editor.IEditorOptions>지정된 된 범위에 대 한.</xref:Microsoft.VisualStudio.Text.Editor.IEditorOptions>|  
|<xref:Microsoft.VisualStudio.Text.Editor.IScrollMapFactoryService></xref:Microsoft.VisualStudio.Text.Editor.IScrollMapFactoryService>|<xref:Microsoft.VisualStudio.Text.Editor.IScrollMap>텍스트 보기에 대 한.</xref:Microsoft.VisualStudio.Text.Editor.IScrollMap>|  
|<xref:Microsoft.VisualStudio.Text.Editor.ISmartIndentationService></xref:Microsoft.VisualStudio.Text.Editor.ISmartIndentationService>|<xref:Microsoft.VisualStudio.Text.Editor.ISmartIndent> <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.</xref:Microsoft.VisualStudio.Text.Editor.ITextView> </xref:Microsoft.VisualStudio.Text.Editor.ISmartIndent>|  
|<xref:Microsoft.VisualStudio.Text.Editor.ISmartIndentationService></xref:Microsoft.VisualStudio.Text.Editor.ISmartIndentationService>|자동 들여쓰기를 가져옵니다는 <xref:Microsoft.VisualStudio.Text.Editor.ISmartIndentProvider>개체.</xref:Microsoft.VisualStudio.Text.Editor.ISmartIndentProvider>|  
|<xref:Microsoft.VisualStudio.Text.Editor.ITextEditorFactoryService></xref:Microsoft.VisualStudio.Text.Editor.ITextEditorFactoryService>|<xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView>.</xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView> </xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> 관리|  
|<xref:Microsoft.VisualStudio.Text.Formatting.IFormattedTextSourceFactoryService></xref:Microsoft.VisualStudio.Text.Formatting.IFormattedTextSourceFactoryService>|An <xref:Microsoft.VisualStudio.Text.Formatting.IFormattedLineSource>.</xref:Microsoft.VisualStudio.Text.Formatting.IFormattedLineSource>|  
|<xref:Microsoft.VisualStudio.Text.Formatting.IRtfBuilderService></xref:Microsoft.VisualStudio.Text.Formatting.IRtfBuilderService>|스냅숏 범위의 집합에서 RTF 서식의 텍스트를 생성합니다.|  
|<xref:Microsoft.VisualStudio.Text.Formatting.ITextAndAdornmentSequencerFactoryService></xref:Microsoft.VisualStudio.Text.Formatting.ITextAndAdornmentSequencerFactoryService>|<xref:Microsoft.VisualStudio.Text.Formatting.ITextAndAdornmentSequencer> <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.</xref:Microsoft.VisualStudio.Text.Editor.ITextView> </xref:Microsoft.VisualStudio.Text.Formatting.ITextAndAdornmentSequencer>|  
|<xref:Microsoft.VisualStudio.Text.Formatting.ITextParagraphPropertiesFactoryService></xref:Microsoft.VisualStudio.Text.Formatting.ITextParagraphPropertiesFactoryService>|A <xref:System.Windows.Media.TextFormatting.TextParagraphProperties>보기에서 텍스트 줄의 서식을 지정 하기 위한.</xref:System.Windows.Media.TextFormatting.TextParagraphProperties>|  
|<xref:Microsoft.VisualStudio.Text.Operations.IEditorOperationsFactoryService></xref:Microsoft.VisualStudio.Text.Operations.IEditorOperationsFactoryService>|<xref:Microsoft.VisualStudio.Text.Operations.IEditorOperations> <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.</xref:Microsoft.VisualStudio.Text.Editor.ITextView> 에 대 한 개체</xref:Microsoft.VisualStudio.Text.Operations.IEditorOperations>|  
|<xref:Microsoft.VisualStudio.Text.Operations.ITextSearchService></xref:Microsoft.VisualStudio.Text.Operations.ITextSearchService>|텍스트 스냅숏을 검색합니다.|  
|<xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService></xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>|<xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigator> <xref:Microsoft.VisualStudio.Text.ITextBuffer> <xref:Microsoft.VisualStudio.Utilities.IContentType>.</xref:Microsoft.VisualStudio.Utilities.IContentType> </xref:Microsoft.VisualStudio.Text.ITextBuffer> </xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigator>|  
|<xref:Microsoft.VisualStudio.Text.Outlining.IOutliningManagerService></xref:Microsoft.VisualStudio.Text.Outlining.IOutliningManagerService>|<xref:Microsoft.VisualStudio.Text.Outlining.IOutliningManager>텍스트 보기에 대 한.</xref:Microsoft.VisualStudio.Text.Outlining.IOutliningManager>|  
|<xref:Microsoft.VisualStudio.Language.Intellisense.IGlyphService></xref:Microsoft.VisualStudio.Language.Intellisense.IGlyphService>|문자 모양의 표준 집합입니다.|  
|<xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseSessionStackMapService></xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseSessionStackMapService>|<xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseSessionStack> <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.</xref:Microsoft.VisualStudio.Text.Editor.ITextView> </xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseSessionStack>|  
|<xref:Microsoft.VisualStudio.Language.Intellisense.IWpfKeyboardTrackingService></xref:Microsoft.VisualStudio.Language.Intellisense.IWpfKeyboardTrackingService>|키보드 처리를 추적 합니다.|  
|<xref:Microsoft.VisualStudio.Language.StandardClassification.IStandardClassificationService></xref:Microsoft.VisualStudio.Language.StandardClassification.IStandardClassificationService>|표준 <xref:Microsoft.VisualStudio.Text.Classification.IClassificationType>개체.</xref:Microsoft.VisualStudio.Text.Classification.IClassificationType>|  
|<xref:Microsoft.VisualStudio.Text.Operations.ITextUndoHistoryRegistry></xref:Microsoft.VisualStudio.Text.Operations.ITextUndoHistoryRegistry>|텍스트 버퍼 간의 관계를 유지 관리 하 고 <xref:Microsoft.VisualStudio.Text.Operations.ITextUndoHistory>개체.</xref:Microsoft.VisualStudio.Text.Operations.ITextUndoHistory>|  
  
## <a name="other-imports"></a>다른 가져오기  
 공급자 팩터리 및 브로커는 일반적으로 여러 구성 요소에서 여러 인스턴스를 가질 수 있는 엔터티입니다.  
  
|가져오기|제공|  
|------------|--------------|  
|<xref:Microsoft.VisualStudio.Text.Adornments.IErrorProviderFactory></xref:Microsoft.VisualStudio.Text.Adornments.IErrorProviderFactory>|<xref:Microsoft.VisualStudio.Text.Tagging.SimpleTagger%601>형식의 <xref:Microsoft.VisualStudio.Text.Tagging.ErrorTag>) 지정된 된 버퍼에 대 한.</xref:Microsoft.VisualStudio.Text.Tagging.ErrorTag> </xref:Microsoft.VisualStudio.Text.Tagging.SimpleTagger%601>|  
|<xref:Microsoft.VisualStudio.Text.Adornments.ITextMarkerProviderFactory></xref:Microsoft.VisualStudio.Text.Adornments.ITextMarkerProviderFactory>|텍스트 표식 태거 (한 <xref:Microsoft.VisualStudio.Text.Tagging.SimpleTagger%601>형식의 <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>).</xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag> </xref:Microsoft.VisualStudio.Text.Tagging.SimpleTagger%601>|  
|<xref:Microsoft.VisualStudio.Text.Adornments.IToolTipProviderFactory></xref:Microsoft.VisualStudio.Text.Adornments.IToolTipProviderFactory>|<xref:Microsoft.VisualStudio.Text.Adornments.IToolTipProvider>주어진 <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.</xref:Microsoft.VisualStudio.Text.Editor.ITextView> </xref:Microsoft.VisualStudio.Text.Adornments.IToolTipProvider>|  
|<xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionBroker></xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionBroker>|An <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSession>.</xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSession>|  
|<xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoBroker></xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoBroker>|An <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSession>.</xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSession>|  
|<xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpBroker></xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpBroker>|An <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSession>.</xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSession>|  
  
## <a name="see-also"></a>참고 항목  
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)
