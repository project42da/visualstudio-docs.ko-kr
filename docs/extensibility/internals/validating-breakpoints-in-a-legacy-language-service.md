---
title: "유효성을 검사 하는 레거시 언어 서비스의 중단점 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- breakpoint validation
- language services [managed package framework], breakpoint validation
ms.assetid: a7e873cd-dfe1-474f-bda5-fd7532774b15
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f8d2f56c29121a4be06f00198edd235007fc1cd0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="validating-breakpoints-in-a-legacy-language-service"></a>유효성을 검사 하는 레거시 언어 서비스의 중단점
중단점은 디버거에 실행 되는 동안 특정 지점에서 프로그램 실행을 중지 해야 함을 나타냅니다. 사용자는 편집기에는 중단점에 대 한 올바른 위치를 구성 하는 항목에 대해 알지 못합니다 소스 파일에서 줄 중단점을 배치할 수 있습니다. 디버거를 시작할 때 실행 중인 프로그램에서 적절 한 위치에는의 모든 표시 된 중단점 (보류 중단점 라고 함)이 바인딩됩니다. 중단점 되도록 유효성을 검사 하는 동시에 유효한 코드 위치 표시 합니다. 예를 들어 메모에 중단점 올바르지 소스 코드의 위치에 있는 코드가 없는 있기 때문에 합니다. 디버거가 잘못 된 중단점을 해제 합니다.  
  
 표시 되 고 소스 코드에 대 한 언어 서비스를 알고 있으므로 검사할 수 중단점 디버거를 시작 하기 전에. 재정의할 수 있습니다는 <xref:Microsoft.VisualStudio.Package.LanguageService.ValidateBreakpointLocation%2A> 중단점의 올바른 위치를 지정 하는 범위를 반환 하는 메서드. 중단점 위치 디버거를 시작할 때 잘못 된 중단점의 디버거를 로드할 때까지 기다리지 않고 사용자가 알림을 계속 유효성이 검사 됩니다.  
  
## <a name="implementing-support-for-validating-breakpoints"></a>중단점 유효성 검사에 대 한 지원 구현  
  
-   <xref:Microsoft.VisualStudio.Package.LanguageService.ValidateBreakpointLocation%2A> 메서드에 중단점의 위치를 제공 됩니다. 구현 위치 올바른지와 코드를 식별 하는 텍스트 범위를 반환 하 여이 연결 된 줄 위치 중단점 표시 여부를 결정 해야 합니다.  
  
-   반환할 <xref:Microsoft.VisualStudio.VSConstants.S_OK> 위치 올바른지 또는 <xref:Microsoft.VisualStudio.VSConstants.S_FALSE> 유효 하지 않을 경우.  
  
-   중단점이 올바르면 텍스트 범위 중단점 함께 강조 표시 됩니다.  
  
-   중단점이 유효 하지 않을 경우 상태 표시줄에 오류 메시지가 나타납니다.  
  
### <a name="example"></a>예제  
 구현을 보여 주는이 예제는 <xref:Microsoft.VisualStudio.Package.LanguageService.ValidateBreakpointLocation%2A> 메서드를 지정된 된 위치에 (해당 되는 경우) 코드의 범위를 가져오려면 파서를 호출 합니다.  
  
 이 예에서는 추가 했다고 가정는 `GetCodeSpan` 메서드는 <xref:Microsoft.VisualStudio.Package.AuthoringSink> 확인 하는 텍스트 범위를 반환 하는 클래스 `true` 중단점이 올바르면 위치인 경우.  
  
```csharp  
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
  
## <a name="see-also"></a>참고 항목  
 [레거시 언어 서비스 기능](../../extensibility/internals/legacy-language-service-features1.md)