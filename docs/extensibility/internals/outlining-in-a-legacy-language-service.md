---
title: "레거시 언어 서비스 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "개요"
  - "언어 서비스 [관리 되는 패키지 프레임 워크] 개요"
  - "개요, 언어 서비스 [관리 되는 패키지 프레임 워크]에서 지 원하는"
ms.assetid: 7b5578b4-a20a-4b94-ad4c-98687ac133b9
caps.latest.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 15
---
# 레거시 언어 서비스 개요
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

개요 표시 하면 복잡 한 프로그램 개요 또는 개요로 축소할 수 있습니다. 예를 들어 C\#에서 모든 메서드는 메서드 시그니처를 표시 하는 한 줄으로 축소할 수 있습니다. 또한 구조체와 클래스는 구조체 및 클래스의 이름만 표시를 축소할 수 있습니다. 메서드 내에서 단일 복잡 한 논리 축소할 수와 같은의 문 첫 번째 줄만 표시 하 여 전체 흐름을 표시 하도록 `foreach`, `if`, 및 `while`합니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 되는 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 새로운 방법입니다. 자세한 내용을 참조 하십시오 [연습: 개요](../../extensibility/walkthrough-outlining.md)합니다.  
  
> [!NOTE]
>  새 편집기 API를 최대한 빨리 사용을 시작 하는 것이 좋습니다. 이 언어 서비스의 성능을 향상 하 고 새로운 편집기 기능을 이용할 수 있도록 합니다.  
  
## 개요에 대 한 지원을 사용 하도록 설정  
 `AutoOutlining` 레지스트리 항목이 자동으로 개요 표시를 사용 하도록 설정 하려면 1로 설정 됩니다. 파일을 로드 하거나 숨겨진된 영역을 식별 하 고 개요 문자 표시 하도록 변경 하는 경우에 전체 소스는 구문 분석을 설정 자동 개요 표시 합니다. 개요 제어할 수도 있습니다 수동으로 사용자가 있습니다.  
  
 값은 `AutoOutlining` 레지스트리 항목을 통해 얻을 수 있습니다는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.AutoOutlining%2A> 속성에는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> 클래스입니다.`AutoOutlining` 레지스트리 항목을 명명된 된 매개 변수 초기화 될 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> 특성 \(참조 [언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md) 대 한 자세한 내용은\).  
  
## 숨겨진된 영역  
 언어 서비스는 개요를 제공 하려면 숨겨진된 영역을 지원 해야 합니다. 이들은 확장 하거나 축소할 수 있는 텍스트 범위입니다. 중괄호로 묶인 같은 표준 언어 기호에 의해 또는 사용자 지정 기호에 의해 숨겨진된 영역을 구분할 수 있습니다. 예를 들어 C\#에 `#region`\/`#endregion` 숨겨진된 영역을 구분 하는 쌍.  
  
 숨겨진된 영역으로 노출 되는 숨겨진된 영역 관리자가 관리 되는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> 인터페이스입니다.  
  
 숨겨진된 영역을 사용 하 여 개요는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenRegion> 인터페이스 및 숨겨진된 영역, 현재 표시 되는 상태, 및 범위를 축소 하는 경우 표시할 배너의 범위를 포함 합니다.  
  
 언어 서비스 파서를 사용 하는 <xref:Microsoft.VisualStudio.Package.AuthoringSink.AddHiddenRegion%2A> 숨겨진된 영역에 대 한 기본 동작과 함께 새로운 숨겨진된 영역을 추가 하는 메서드 동안는 <xref:Microsoft.VisualStudio.Package.AuthoringSink.AddHiddenRegion%2A> 메서드를 사용 하면 모양 및 개요의 동작을 사용자 지정할 수 있습니다. 숨겨진된 영역의 숨겨진된 영역 세션에 부여 되 면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 언어 서비스에 대 한 숨겨진된 영역을 관리 합니다.  
  
 숨겨진된 영역 세션 소멸 될 때를 결정 해야 하는 경우 숨겨진된 영역 변경 되었거나 특정 숨겨진된 영역; 표시 되는지 확인 해야 합니다. 클래스를 파생 해야는 <xref:Microsoft.VisualStudio.Package.Source> 클래스 및 적절 한 메서드를 재정의 <xref:Microsoft.VisualStudio.Package.Source.OnBeforeSessionEnd%2A>, <xref:Microsoft.VisualStudio.Package.Source.OnHiddenRegionChange%2A>, 및 <xref:Microsoft.VisualStudio.Package.Source.MakeBaseSpanVisible%2A>, 각각.  
  
### 예제  
 모든 중괄호 쌍에 대 한 숨겨진된 영역을 만드는 간단한 예는 다음과 같습니다. 가정 언어 중괄호 일치를 제공 하 고 일치 시킬 중괄호 포함 적어도 중괄호 \({및}\). 이 방법은 설명을 위한 용도로 합니다. 전체 구현 사례를 전체 처리는 것이 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A>합니다. 또한이 예에서는 설정 하는 방법을 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.AutoOutlining%2A> 우선 `true` 일시적으로 합니다. 대신 지정 하는 것은 `AutoOutlining` 명명 된 매개 변수와 `ProvideLanguageServiceAttribute` 언어 패키지에는 특성입니다.  
  
 이 예에서는 C\# 주석, 문자열 및 리터럴에 대 한 규칙을 가정 합니다.  
  
```c#  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace MyLanguagePackage  
{  
  
    public class MyLanguageService : LanguageService  
    {  
        private LanguagePreferences m_preferences;  
  
        public override LanguagePreferences  GetLanguagePreferences()  
        {  
            if (m_preferences == null)  
            {  
                m_preferences = new LanguagePreferences(this.Site,  
                                                        typeof(MyLanguageService).GUID,  
                                                        Name);  
                m_preferences.Init();  
                // Temporarily enabled auto-outlining  
                m_preferences.AutoOutlining = true;  
            }  
            return m_preferences;  
        }  
  
        public override AuthoringScope  ParseSource(ParseRequest req)  
        {  
            Source source = (Source) this.GetSource(req.FileName);  
            switch (req.Reason)  
            {  
               case ParseReason.HighlightBraces:  
               case ParseReason.MatchBraces:  
               case ParseReason.MemberSelectAndHighlightBraces:  
                  if (source.Braces != null)  
                  {  
                      foreach (TextSpan[] brace in source.Braces)  
                      {  
                         if (brace.Length == 2)  
                         {  
                             if (req.Sink.HiddenRegions == true   
                                   && source.GetText(brace[0]).Equals("{")   
                                   && source.GetText(brace[1]).Equals("}"))  
                             {  
                                //construct a TextSpan of everything between the braces  
                                TextSpan hideSpan = new TextSpan();  
                                hideSpan.iStartIndex = brace[0].iStartIndex;  
                                hideSpan.iStartLine = brace[0].iStartLine;  
                                hideSpan.iEndIndex = brace[1].iEndIndex;  
                                hideSpan.iEndLine = brace[1].iEndLine;  
                                req.Sink.ProcessHiddenRegions = true;  
                                req.Sink.AddHiddenRegion(hideSpan);  
                             }  
                             req.Sink.MatchPair(brace[0], brace[1], 1);  
                         }  
                         else if (brace.Length >= 3)  
                             req.Sink.MatchTriple(brace[0], brace[1], brace[2], 1);  
                  }  
        }  
                   break;  
               default:  
                   break;  
      }  
            // Must always return a valid AuthoringScope object.  
            return new MyAuthoringScope();  
        }  
    }  
}  
```  
  
## 참고 항목  
 [레거시 언어 서비스 기능](../../extensibility/internals/legacy-language-service-features1.md)   
 [언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md)