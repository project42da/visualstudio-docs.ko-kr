---
title: "레거시 언어 서비스에서 자동 창에 대 한 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- language services [managed package framework], Autos window
- Autos window, supporting in language services [managed package framework]
ms.assetid: 47d40aae-7a3c-41e1-a949-34989924aefb
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c824845d4cbdb58241c088c1cb30259d3c298f72
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="support-for-the-autos-window-in-a-legacy-language-service"></a>레거시 언어 서비스에서 자동 창에 대 한 지원
**자동** 디버깅 중인 프로그램 (중 하나 중단점 또는 예외 발생) 일시 중지 되 면 범위에 있는 매개 변수 및 변수와 같은 식 창에 표시 됩니다. 식은 변수, 지역 또는 전역 및 로컬 범위에서 변경 된 매개 변수를 포함할 수 있습니다. **자동** 창 클래스, 구조체 또는 일부 다른 형식이의 인스턴스화를 포함할 수도 있습니다. 식 계산기를 평가할 수 있는 모든 항목에 잠재적으로 표시할 수는 **자동** 창.  
  
 에 대 한 직접 지원 MPF ()는 관리 패키지 프레임 워크는 **자동** 창. 그러나 재정의 하는 경우는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetProximityExpressions%2A> 메서드를에 표시 되는 식의 목록을 반환할 수 있습니다는 **자동** 창.  
  
## <a name="implementing-support-for-the-autos-window"></a>자동 창에 대 한 지원 구현  
 지원 하기 위해 수행 하기만 하면는 **자동** 창을 구현 하는 것은 <xref:Microsoft.VisualStudio.Package.LanguageService.GetProximityExpressions%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스. 식에 표시 되어야 하는 소스 파일의 위치를 받아야 구현 결정 해야는 **자동** 창. 메서드는 각 문자열 나타내는 단일 식 문자열의 목록을 반환 합니다. 반환 값이 <xref:Microsoft.VisualStudio.VSConstants.S_OK> 식 목록에 포함 되어 있음을 나타냅니다 동안 <xref:Microsoft.VisualStudio.VSConstants.S_FALSE> 표시할 식이 없는 있음을 나타냅니다.  
  
 반환 된 실제 식을 변수 또는 코드에서 해당 위치에 표시 되는 매개 변수의 이름입니다. 이러한 이름은 다음에 표시 되는 형식 및 값을 식 계산기에 전달 되는 **자동** 창.  
  
### <a name="example"></a>예제  
 다음 예제에서는의 구현을 보여 줍니다.는 <xref:Microsoft.VisualStudio.Package.LanguageService.GetProximityExpressions%2A> 에서 식의 목록을 가져오는 메서드를는 <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> 구문 분석 하는 이유를 사용 하 여 메서드 <xref:Microsoft.VisualStudio.Package.ParseReason>합니다. 로 래핑된 식 각각는 `TestVsEnumBSTR` 구현 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsEnumBSTR> 인터페이스입니다.  
  
 `GetAutoExpressionsCount` 및 `GetAutoExpression` 메서드에 사용자 지정 메서드는는 `TestAuthoringSink` 개체 및이 예제를 지원 하기 위해 추가 되었습니다. 에 추가 하는 식에는 한 가지 방법은 나타내는 `TestAuthoringSink` 파서에서 개체 (호출 하 여는 <xref:Microsoft.VisualStudio.Package.AuthoringSink.AutoExpression%2A> 메서드) 파서가 외부에서 액세스할 수 있습니다.  
  
```csharp  
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