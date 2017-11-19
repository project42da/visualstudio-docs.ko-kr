---
title: "검사 목록: 레거시 언어 서비스를 만드는 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- language services
- language services, native code
ms.assetid: 8b73b341-a33a-4ab5-9390-178c9e563d2d
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5c06d246f7467e19969075537f321061463d1755
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="checklist-creating-a-legacy-language-service"></a>검사 목록: 레거시 언어 서비스 만들기
다음 검사 목록에 대 한 언어 서비스를 만들기 위해 수행 해야 하는 기본 단계를 요약는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 코어 편집기입니다. 언어 서비스에 통합할 수 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 디버그 식 계산기를 만들어야 합니다. 자세한 내용은 참조 [CLR 식 계산기 작성](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md) 에 [Visual Studio 디버거 확장성](../../extensibility/debugger/visual-studio-debugger-extensibility.md)합니다.  
  
## <a name="steps-for-creating-a-language-service"></a>언어 서비스를 만드는 단계  
  
1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> 인터페이스를 구현합니다.  
  
    -   VSPackage, 구현에서 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> 언어 서비스를 제공 하는 인터페이스입니다.  
  
    -   언어 서비스의 통합된 개발 환경 (IDE)를 사용할 수 있도록 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> 구현 합니다.  
  
2.  구현 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> 주 언어 서비스 클래스의 인터페이스입니다.  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> 인터페이스는 코어 편집기와 언어 서비스 간의 상호 작용의 시작 지점입니다.  
  
### <a name="optional-features"></a>선택적 기능  
 다음과 같은 기능이 선택 사항이 며 순서에 관계 없이 구현 될 수 있습니다. 이러한 기능에는 언어 서비스의 기능 향상.  
  
-   구문 색 지정  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> 인터페이스를 구현합니다. 이 인터페이스의 구현에 적절 한 색 정보를 반환 하는 파서 정보를 해야 합니다.  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> 메서드가 반환 되는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> 인터페이스입니다. 구현 해야 하므로 각 텍스트 버퍼에 대 한 별도 색 지정 기 인스턴스가 만들어집니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> 별도로 인터페이스입니다. 자세한 내용은 참조 [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)합니다.  
  
-   코드 창  
  
     구현 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> 언어 서비스는 새 코드 창 만들어질 때 알림을 받을 수 있도록 하는 인터페이스입니다.  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetCodeWindowManager%2A> 메서드가 반환 되는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> 인터페이스입니다. 언어 서비스의 코드 창에 특수 UI 추가할 수 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.AddAdornments%2A>합니다. 언어 서비스의 보기 필터 텍스트를 추가 하는 등의 특수 한 처리를 수행할 수도 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.OnNewView%2A>합니다.  
  
-   텍스트 뷰 필터  
  
     IntelliSense 문 완성에서 언어 서비스를 제공 하려면 텍스트 보기 처리할 수 있는 명령 중 일부를 차단 해야 합니다. 이러한 명령은 가로채기 위해 다음 단계를 수행 합니다.  
  
    -   구현 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 핸들 편집기 명령과 명령 체인에에서 참여할 수 있습니다.  
  
    -   호출의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> 메서드를 전달 하면 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 구현 합니다.  
  
    -   호출 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.RemoveCommandFilter%2A> 메서드 이러한 명령에 전달 더 이상 되도록 보기에서 분리 하는 경우.  
  
     처리 해야 하는 명령을 제공 하는 서비스에 따라 달라 집니다. 자세한 내용은 참조 [언어 서비스 필터에 대 한 중요 한 명령을](../../extensibility/internals/important-commands-for-language-service-filters.md)합니다.  
  
    > [!NOTE]
    >  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> 와 같은 개체에 인터페이스를 구현 해야는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스입니다.  
  
-   문 완성   
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> 인터페이스를 구현합니다.  
  
     문 완성 명령을 지원 (즉, <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>)를 호출 하 고는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 인터페이스를 전달는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> 인터페이스입니다. 자세한 내용은 참조 [레거시 언어 서비스에서 문 완성](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md)합니다.  
  
-   메서드 팁  
  
     구현 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData> 메서드 팁 창에 대 한 데이터를 제공 하는 인터페이스입니다.  
  
     메서드가 데이터 팁 창 표시 하는 시기를 알 수 있도록 명령을 적절 하 게 처리할 수 텍스트 뷰 필터를 설치 합니다. 자세한 내용은 참조 [레거시 언어 서비스에 대 한 매개 변수 정보](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md)합니다.  
  
-   오류 표식  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 인터페이스를 구현합니다.  
  
     오류 구현 하는 표식 개체 만들기는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 인터페이스 및 호출은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> 전달 하는 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 오류 표식 개체의 인터페이스입니다.  
  
     일반적으로 각 오류 표식 작업 목록 창에 있는 항목을 관리합니다.  
  
-   작업 목록 항목  
  
     구현 된 작업 항목 클래스를 제공 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem> 인터페이스입니다.  
  
     구현 된 작업 공급자 클래스를 제공 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider> 인터페이스 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider2> 인터페이스입니다.  
  
     구현 된 작업 열거자 클래스를 제공 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumTaskItems> 인터페이스입니다.  
  
     작업 목록에 작업 공급자를 등록 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList.RegisterTaskProvider%2A> 메서드.  
  
     가져올는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList> 서비스 GUID와 언어 서비스의 서비스 공급자를 호출 하 여 인터페이스 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList>합니다.  
  
     작업 항목 개체를 만들고 호출은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList.RefreshTasks%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList> 없으면 새 인터페이스 또는 작업을 업데이트 합니다.  
  
-   주석 작업 항목  
  
     사용 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCommentTaskInfo> 인터페이스 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumCommentTaskTokens> 주석 작업 토큰을 얻는 데 인터페이스입니다.  
  
     가져올는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCommentTaskInfo> 에서 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList> 서비스입니다.  
  
     가져올는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumCommentTaskTokens> 에서 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCommentTaskInfo.EnumTokens%2A> 메서드.  
  
     구현 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskListEvents> 토큰 목록에 변경 내용을 수신 대기 하는 인터페이스입니다.  
  
-   개요  
  
     개요 기능을 지원 하기 위한 몇 가지 옵션이 있습니다. 예를 들어 지원할 수 있습니다는 **정의 부분만** 명령, 편집기 제어 개요 영역을 제공 하거나 클라이언트에서 제어 되는 영역을 지원 합니다. 자세한 내용은 참조 [하는 방법: 제공 확장 개요 지원 레거시 언어 서비스의](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)합니다.  
  
-   언어 서비스 등록  
  
     언어 서비스를 등록 하는 방법에 대 한 자세한 내용은 참조 [레거시 언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service2.md) 및 [관리 Vspackage](../../extensibility/managing-vspackages.md)합니다.  
  
-   상황에 맞는 도움말  
  
     다음 방법 중 하나에 편집기에 컨텍스트를 제공 합니다.  
  
    -   텍스트 표식에 대 한 컨텍스트를 구현 하 여 제공 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> 인터페이스입니다.  
  
 구현 하 여 모든 사용자 컨텍스트를 제공는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [레거시 언어 서비스 개발](../../extensibility/internals/developing-a-legacy-language-service.md)   
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)