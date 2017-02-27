---
title: "검사 목록: 레거시 언어 서비스 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "언어 서비스"
  - "언어 서비스, 네이티브 코드"
ms.assetid: 8b73b341-a33a-4ab5-9390-178c9e563d2d
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# 검사 목록: 레거시 언어 서비스 만들기
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다음 검사 목록에 대 한 언어 서비스를 만들기 위해 수행 해야 하는 기본 단계 요약 한의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 코어 편집기입니다.  언어 서비스에 통합 하는 데 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 디버그 식 계산기를 만들어야 합니다.  자세한 내용은 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md) 에 [Visual Studio 디버거 확장성](../../extensibility/debugger/visual-studio-debugger-extensibility.md).  
  
## 언어 서비스를 만드는 단계  
  
1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> 인터페이스를 구현합니다.  
  
    -   구현 하면 Vspackage에는 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> 언어 서비스를 제공 하는 인터페이스입니다.  
  
    -   언어 서비스를 통합된 개발 환경 \(IDE\)에서 사용할 수 있도록 사용자 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> 구현 합니다.  
  
2.  구현에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> 주 언어 서비스 클래스의 인터페이스입니다.  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> 인터페이스 코어 편집기와 언어 서비스 간의 상호 작용의 시작 지점입니다.  
  
### 선택적 기능  
 다음 기능은 선택적 이며 순서에 관계 없이 구현할 수 있습니다.  이러한 기능은 언어 서비스의 기능을 증가합니다.  
  
-   구문 색 지정  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> 인터페이스를 구현합니다.  적절 한 색 정보를 반환 하는 파서 정보가이 인터페이스의 구현을 사용 해야 합니다.  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> 메서드가 반환의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> 인터페이스입니다.  구현 해야 하므로 각 텍스트 버퍼에 대 한 별도 colorizer 인스턴스 생성 됩니다 있는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> 별도로 인터페이스.  자세한 내용은 [구문 레거시 언어 서비스에 색 지정](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)를 참조하십시오.  
  
-   코드 창  
  
     구현에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> 인터페이스의 새 코드 창을 만들 때 알림 메시지를 받으려면 언어 서비스를 사용 하도록 합니다.  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetCodeWindowManager%2A> 메서드가 반환의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> 인터페이스입니다.  언어 서비스 특별 한 UI를 코드 창에 다음 추가할 수 있습니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.AddAdornments%2A>.  언어 서비스에서 텍스트 보기 필터 추가 같은 특수 처리를 수행할 수도 있습니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.OnNewView%2A>.  
  
-   필터 텍스트 보기  
  
     IntelliSense 문 완성 언어 서비스를 제공 하기 위해 일부 텍스트 보기 처리 합니다. 그렇지 않은 경우 명령은 차단 해야 합니다.  이러한 명령을 차단 하려면 다음 단계를 완료 하십시오.  
  
    -   구현 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 명령 체인 및 핸들 편집기 명령에 참여할 수 있습니다.  
  
    -   호출 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> 메서드 및 패스에서를 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 구현.  
  
    -   호출 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.RemoveCommandFilter%2A> 이러한 명령을 더 이상 전달 되는 보기를 분리할 때 메서드.  
  
     처리 해야 하는 명령을 제공 하는 서비스에 따라 달라 집니다.  자세한 내용은 [언어 서비스 필터에 대 한 중요 한 명령](../../extensibility/internals/important-commands-for-language-service-filters.md)를 참조하십시오.  
  
    > [!NOTE]
    >  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> 와 같은 개체에서 인터페이스를 구현 해야 합니다는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스입니다.  
  
-   문 완성  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> 인터페이스를 구현합니다.  
  
     문 완성 명령을 지원 \(, <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>\)를 호출 하 고는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> 메서드에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 인터페이스를 전달 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> 인터페이스.  자세한 내용은 [레거시 언어 서비스에서 문 완성](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md)를 참조하십시오.  
  
-   방법 팁  
  
     구현에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData> 메서드 팁 창에 대 한 데이터를 제공 하는 인터페이스입니다.  
  
     메서드 데이터 팁 창에 표시 하는 시기를 알 수 있도록 명령을 적절 하 게 처리 하 여 텍스트 보기 필터를 설치 합니다.  자세한 내용은 [레거시 언어 서비스의 매개 변수 정보](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md)를 참조하십시오.  
  
-   오류 표식  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 인터페이스를 구현합니다.  
  
     구현 표식 개체 오류를 만들는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 인터페이스와 호출의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> 메서드를 전달 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 오류 표식 개체의 인터페이스.  
  
     일반적으로 각 오류 표식 작업 목록 창에서 항목을 관리합니다.  
  
-   작업 목록 항목  
  
     작업 항목 클래스 제공 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem> 인터페이스입니다.  
  
     구현 작업 공급자 클래스가 제공의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider> 인터페이스와 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider2> 인터페이스입니다.  
  
     구현 된 작업 열거자 클래스를 제공 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumTaskItems> 인터페이스입니다.  
  
     작업 목록의 작업이 공급자 등록 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList.RegisterTaskProvider%2A> 메서드가 있습니다.  
  
     얻기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList> 인터페이스는 서비스 GUID와 언어 서비스의 서비스 공급자를 호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList>.  
  
     작업 항목 개체를 만들고 호출이 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList.RefreshTasks%2A> 메서드에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList> 있을 때 새로운 인터페이스 또는 작업 업데이트.  
  
-   작업 항목 설명  
  
     사용의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCommentTaskInfo> 인터페이스와 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumCommentTaskTokens> 주석 작업 토큰을 얻을 수 있는 인터페이스입니다.  
  
     얻기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCommentTaskInfo> 에서 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList> 서비스 합니다.  
  
     얻기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumCommentTaskTokens> 에서 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCommentTaskInfo.EnumTokens%2A> 메서드.  
  
     구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskListEvents> 토큰 목록에 대 한 변경 내용을 수신 대기 하는 인터페이스입니다.  
  
-   개요  
  
     개요를 지 원하는 몇 가지 옵션이 있습니다.  지원할 수 있습니다 예를 들어, 있는  **정의 부분만 보이기** 명령, 제어 편집기 개요 영역을 제공 하거나 클라이언트 제어 영역을 지원 합니다.  자세한 내용은 [방법: 레거시 언어 서비스의 확장 된 개요 지원 제공](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)를 참조하십시오.  
  
-   언어 서비스 등록  
  
     언어 서비스를 등록 하는 방법에 대 한 자세한 내용은 참조 하십시오. [레거시 언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service2.md) 및 [Vspackage를 관리합니다.](../../extensibility/managing-vspackages.md).  
  
-   상황에 맞는 도움말  
  
     컨텍스트 편집기를 다음 방법 중 하나를 제공 합니다.  
  
    -   텍스트 마커를 구현 하 여 컨텍스트를 제공은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> 인터페이스입니다.  
  
 구현 하 여 모든 사용자 컨텍스트를 제공은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> 인터페이스입니다.  
  
## 참고 항목  
 [언어 서비스 개발](../../extensibility/internals/developing-a-legacy-language-service.md)   
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)