---
title: "레거시 언어 서비스의 자동 창에 대 한 지원 | Microsoft Docs"
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
  - "언어 서비스 [관리 되는 패키지 프레임 워크] 자동 창"
  - "언어 서비스 [관리 되는 패키지 프레임 워크]에서 지 원하는 자동 창"
ms.assetid: 47d40aae-7a3c-41e1-a949-34989924aefb
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 레거시 언어 서비스의 자동 창에 대 한 지원
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

해당  **자동** 변수 및 디버깅 중인 프로그램 \(중 예외 또는 중단점으로 인해\) 일시 중지 된 경우 범위에 있는 매개 변수의 예 식 창에 표시 됩니다.  식 로컬 또는 전역 변수 및 로컬 범위에서 변경 된 매개 변수를 포함할 수 있습니다.  **자동** 창 클래스, 구조체 또는 다른 종류의 인스턴스화 포함 될 수 있습니다 수도 있습니다.  식 계산기가 계산할 수 있는 가능성이 있는을 표시할 수 있는  **자동** 창입니다.  
  
 패키지 관리 프레임 워크 \(MPF\)에 대 한 직접 지원을 제공 하지 않습니다을  **자동** 창입니다.  그러나 재정의할 경우는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetProximityExpressions%2A> 메서드, 식에 표시 하려면 목록을 반환할 수 있습니다 해당  **자동** 창.  
  
## 자동 창에 대 한 지원을 구현합니다.  
 지원 하기 위해 필요한 모든는  **자동** 창인 구현 하는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetProximityExpressions%2A> 메서드에서 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스.  표현식에 나타나야 합니다 소스 파일에서 위치를 지정 하 여 구현 결정 해야의  **자동** 창입니다.  메서드는 단일 식 각 문자열을 나타내는 문자열 목록을 반환 합니다.  반환 값이 <xref:Microsoft.VisualStudio.VSConstants.S_OK> 목록의 식에 포함 되어 있음을 나타냅니다 있지만 <xref:Microsoft.VisualStudio.VSConstants.S_FALSE> 없는 식이 표시 됨을 나타냅니다.  
  
 반환 되는 실제 식의 코드에서 해당 위치를 표시 하는 매개 변수 또는 변수 이름입니다.  이러한 이름은 식 계산기에 표시 되는 형식 및 값을 얻을 수에 전달 되는  **자동** 창.  
  
### 예제  
 구현 하는 다음 예제에 나와 있는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetProximityExpressions%2A> 식의 목록을 가져오는 방법의 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 구문 분석 하는 이유를 사용 하는 방법 <xref:Microsoft.VisualStudio.Package.ParseReason>.  각 식으로 줄 바꿈되는 `TestVsEnumBSTR` 구현 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsEnumBSTR> 인터페이스.  
  
 참고는 `GetAutoExpressionsCount` 및 `GetAutoExpression` 메서드는 사용자 지정 방법에는 `TestAuthoringSink` 및 개체이 예제를 지원 하기 위해 추가 되었습니다.  가지 방법에 추가 하는 식으로 표현는 `TestAuthoringSink` 개체는 파서에서 \(전화는 <xref:Microsoft.VisualStudio.Package.AuthoringSink.AutoExpression%2A> 메서드\) 파서가 외부에 액세스할 수 있습니다.  
  
```c#  
using Microsoft.VisualStudio;  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        public override int GetProximityExpressions(IVsTextBuffer buffer,  
                                                    int line,  
                                                    int col,  
                                                    int cLines,  
                                                    out IVsEnumBSTR ppEnum)  
        {  
            int retval = VSConstants.E_NOTIMPL;  
            ppEnum = null;  
            if (buffer != null)  
            {  
                IVsTextLines textLines = buffer as IVsTextLines;  
                if (textLines != null)  
                {  
                    Source src = this.GetSource(textLines);  
                    if (src != null)  
                    {  
                        TokenInfo tokenInfo = new TokenInfo();  
                        string text = src.GetText();  
                        ParseRequest req = CreateParseRequest(src,  
                                                              line,  
                                                              col,  
                                                              tokenInfo,  
                                                              text,  
                                                              src.GetFilePath(),  
                                                              ParseReason.Autos,  
                                                              null);  
                        req.Scope = this.ParseSource(req);  
                        TestAuthoringSink sink = req.Sink as TestAuthoringSink;  
  
                        retval = VSConstants.S_FALSE;  
                        int spanCount = sink.GetAutoExpressionsCount();  
                        if (spanCount > 0) {  
                            TestVsEnumBSTR bstrList = new TestVsEnumBSTR();  
                            for (int i = 0; i < spanCount; i++)  
                            {  
                                TextSpan span;  
                                sink.GetAutoExpression(i, out span);  
                                string expression = src.GetText(span.iStartLine,  
                                                                span.iStartIndex,  
                                                                span.iEndLine,  
                                                                span.iEndIndex);  
                                bstrList.AddString(expression);  
                            }  
                            ppEnum = bstrList;  
                            retval = VSConstants.S_OK;  
                        }  
                    }  
                }  
            }  
            return retval;  
        }  
    }  
}  
```