---
title: "레거시 언어 서비스에 있는 중단점의 유효성 검사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "중단점 유효성 검사"
  - "언어 서비스 [관리 되는 패키지 프레임 워크] 중단점 유효성 검사"
ms.assetid: a7e873cd-dfe1-474f-bda5-fd7532774b15
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# 레거시 언어 서비스에 있는 중단점의 유효성 검사
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버거에서 실행 되는 동안 특정 지점에서 프로그램 실행을 중단 합니다 중단점을 나타냅니다.  편집기 올바른 위치 중단점에 대 한 구성에 대 한 지식이 없기 때문 사용자 소스 파일 줄에서 중단점을 배치할 수 있습니다.  디버거를 시작할 때 표시 된 중단점 \(보류 중단점 이라고 함\)의 모든 실행 중인 프로그램에서 해당 위치에 바인딩되어 있습니다.  중단점 확인 합니다 유효성을 검사 한 번에는 유효한 코드 위치를 표시 합니다.  소스 코드에서 해당 위치의 코드가 없으므로 예를 들어, 중단점을 메모에 올바르지 않습니다.  디버거에서 잘못 된 중단점을 해제 합니다.  
  
 표시 되는 소스 코드에 대 한 언어 서비스를 알고 있으므로 디버거를 시작 하기 전에 중단점을 확인할 수 있습니다.  재정의할 수 있는 <xref:Microsoft.VisualStudio.Package.LanguageService.ValidateBreakpointLocation%2A> 중단점에 대 한 올바른 위치를 지정 하는 범위를 반환 하는 메서드.  중단점 위치에 여전히 디버거가 시작 되 고 사용자의 잘못 된 중단점 디버거를 로드를 기다리지 않고 알립니다 때 유효성이 검사 됩니다.  
  
## 중단점을 확인 하는 지원 구현  
  
-   <xref:Microsoft.VisualStudio.Package.LanguageService.ValidateBreakpointLocation%2A> 메서드는 중단점의 위치를 지정 합니다.  구현 위치 유효 하 고 코드를 식별 하는 텍스트 범위를 반환 하 여이 중단점이 줄 위치와 관련 된 표시 여부를 결정 해야 합니다.  
  
-   반환 <xref:Microsoft.VisualStudio.VSConstants.S_OK> 위치가 잘못 된 경우 또는 <xref:Microsoft.VisualStudio.VSConstants.S_FALSE> 유효 하지 않은 경우.  
  
-   중단점이 잘못 되었습니다 경우 텍스트 범위와 함께 중단점이 강조 표시 됩니다.  
  
-   중단점이 잘못 된 경우 오류 메시지가 상태 표시줄에 표시 됩니다.  
  
### 예제  
 구현 하는 보여 주는이 예제는 <xref:Microsoft.VisualStudio.Package.LanguageService.ValidateBreakpointLocation%2A> 파서에서 코드의 범위 \(있는 경우\)를 얻을 수를 지정 된 위치에 호출 메서드.  
  
 추가 하는 예제는 `GetCodeSpan` 메서드에 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 텍스트 범위 및 반환 확인 클래스 `true` 올바른 중단점 위치 이면.  
  
```c#  
using Microsoft VisualStudio;  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    class TestLanguageService : LanguageService  
    {  
        public override int ValidateBreakpointLocation(IVsTextBuffer buffer,  
                                                       int line,  
                                                       int col,  
                                                       TextSpan[] pCodeSpan)  
        {  
            int retval = VSConstants.S_FALSE;  
            if (pCodeSpan != null)  
            {  
                // Initialize span to current line by default.  
                pCodeSpan[0].iStartLine = line;  
                pCodeSpan[0].iStartIndex = col;  
                pCodeSpan[0].iEndLine = line;  
                pCodeSpan[0].iEndIndex = col;  
            }  
  
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
                                                              ParseReason.CodeSpan,  
                                                              null);  
                        req.Scope = this.ParseSource(req);  
                        TestAuthoringSink sink = req.Sink as TestAuthoringSink;  
  
                        TextSpan span = new TextSpan();  
                        if (sink.GetCodeSpan(out span))  
                        {  
                            pCodeSpan[0] = span;  
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
  
## 참고 항목  
 [레거시 언어 서비스 기능](../../extensibility/internals/legacy-language-service-features1.md)