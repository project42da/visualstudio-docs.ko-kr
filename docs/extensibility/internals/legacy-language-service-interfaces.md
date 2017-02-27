---
title: "레거시 언어 서비스 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IVsLanguageInfo 인터페이스"
  - "언어 서비스, 개체"
ms.assetid: 03b2d507-f463-417e-bc22-bdac68eeda52
caps.latest.revision: 24
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 24
---
# 레거시 언어 서비스 인터페이스
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

특정 프로그래밍 언어에 대 한 수는 언어 서비스의 인스턴스가 하나만 한 번에 있습니다.  그러나 단일 언어 서비스는 둘 이상의 편집기를 사용할 수 있습니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]언어 서비스 특정 편집기와 연결 되지 않습니다.  따라서 언어 서비스 작업을 요청할 때 적절 한 편집기를 매개 변수로 식별 해야 합니다.  
  
## 언어 서비스와 관련 된 공통 인터페이스  
 언어 서비스를 호출 하 여 편집기를 가져옵니다 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A> 적절 한 Vspackage를 합니다.  요청 되는 언어 서비스 식별자 \(SID\)이이 호출에서 전달 되는 서비스를 식별 합니다.  
  
 별도 클래스에서 다양 한 핵심 언어 서비스가 인터페이스를 구현할 수 있습니다.  그러나 일반적인 방법은 단일 클래스에 다음과 같은 인터페이스를 구현 하는 것:  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageBlock>\(선택적 요소\)  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> 의 모든 언어 서비스 인터페이스를 구현 해야 합니다.  언어는 colorizer 검색 하는 언어 서비스와 연결 된 파일 이름 확장명의 지역화 된 이름 등을 언어 서비스에 대 한 정보를 제공 합니다.  
  
## 추가 언어 서비스 인터페이스  
 다른 인터페이스 언어 서비스를 제공할 수 있습니다.  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]텍스트 버퍼의 각 인스턴스에 대해 이러한 인터페이스의 개별 인스턴스를 요청합니다.  따라서 이러한 각 인터페이스의 고유한 개체에서 구현 해야 합니다.  다음 표에서 텍스트 버퍼 인스턴스 당 하나의 인스턴스를 필요로 하는 인터페이스를 보여 줍니다.  
  
|Interface|설명|  
|---------------|--------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager>|코드 창 장식을 드롭다운 표시줄로 등을 관리합니다.  이 인터페이스를 사용 하 여 얻을 수 있습니다의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetCodeWindowManager%2A> 메서드가 있습니다.  하나의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> 코드 창 당.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>|구분 기호 및 언어 키워드 색을 지정 합니다.  이 인터페이스를 사용 하 여 얻을 수 있습니다의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> 메서드가 있습니다.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>페인트 시간에 호출 됩니다.  내부 계산 위주의 작업을 하지 않도록 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> 또는 성능에 문제가 생길 수 있습니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData>|IntelliSense 매개 변수가 도구 설명을 제공합니다.  메서드가 데이터를 나타내는 문자 형식 언어 서비스를 인식 하는 경우에 괄호와 같은 표시 호출을 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow.SetMethodData%2A> 텍스트를 알리는 방법을 볼는 언어 서비스 매개 변수 정보 도구 설명에 표시할 수 있습니다.  텍스트 보기 다음 다시 언어 서비스에서의 메서드를 사용 하 여 호출을 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData> 인터페이스 도구 설명을 표시 하려면 필요한 정보를 얻을 수 있습니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet>|IntelliSense 문 완성을 제공합니다.  언어 서비스 완성 목록에 표시할 수 있습니다 경우 호출 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> 메서드는 텍스트 보기에서.  텍스트 보기 다음 다시 언어 서비스에서 메서드를 사용 하 여 호출을 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> 개체입니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter>|명령 처리기를 사용 하 여 텍스트 뷰를 수정할 수 있습니다.  구현 하는 클래스는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> 인터페이스를 구현 해야 합니다도 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스입니다.  텍스트 보기 검색은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> 개체를 쿼리 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 로 전달 된 개체는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> 메서드.  하나의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> 각 보기에 대 한 개체입니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|사용자 코드 창에 입력 하는 명령을 차단 합니다.  모니터링 결과 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 구현을 완료 사용자 지정 정보를 제공 하 고 수정을 볼 수<br /><br /> 전달 하 여 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 개체에 있는 텍스트 보기를 호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A>.|  
  
## 참고 항목  
 [언어 서비스 개발](../../extensibility/internals/developing-a-legacy-language-service.md)   
 [검사 목록: 레거시 언어 서비스 만들기](../../extensibility/internals/checklist-creating-a-legacy-language-service.md)