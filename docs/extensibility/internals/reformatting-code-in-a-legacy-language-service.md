---
title: 레거시 언어 서비스의 코드를 다시 포맷 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- reformatting code, supporting in language services [managed package framework]
- language services [managed package framework], reformatting code
ms.assetid: 08bb3375-8fef-4f4e-9efa-0d7333bab0eb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 392afbafc2ce15dbf7ee347efdf24ce1f7fe2301
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="reformatting-code-in-a-legacy-language-service"></a>레거시 언어 서비스의 코드를 다시 포맷

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 들여쓰기 및 공백 정규화 하 여 소스 코드를 다시 포맷할 수 있습니다. 여기에 삽입 또는 공백이 나 탭 각 줄의 시작 부분에서 제거, 줄 사이 새 줄을 추가 하거나 공간 탭 또는 탭을 공백으로 바꾸면 포함 됩니다.  
  
>**참고:** 삽입 또는 줄 바꿈 문자 삭제 표식 중단점 및 책갈피와 같은 문제가 발생할 수 있습니다 하지만 공백이 나 탭 추가 또는 제거 표식에 영향을 주지 않습니다.  
  
사용자가 선택 하 여 형식을 변경 작업을 시작할 수 **선택 영역 서식** 또는 **문서 서식** 에서 **고급** 메뉴에는 **편집**메뉴. 코드 조각 또는 특정 문자를 삽입할 때 형식을 변경 작업을 트리거할 수도 있습니다. 예를 들어 C#에서 닫는 중괄호를 입력 하면 일치 하는 여는 중괄호 및 닫는 중괄호 사이 있는 모든 경우에 적절 한 수준으로 자동으로 들여쓰기 있습니다.
  
때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 보냅니다는 **선택 영역 서식** 또는 **문서 서식** 명령을 언어 서비스에는 <xref:Microsoft.VisualStudio.Package.ViewFilter> 호출 클래스는 <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.Source> 클래스입니다. 재정의 해야 형식을 지원 하기 위해는 <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A> 메서드와 공급 장치 코드 고유한 서식 지정 합니다.  
  
## <a name="enabling-support-for-reformatting"></a>다시 포맷 하는 것에 대 한 지원을 사용 하도록 설정  

서식 지정을 지원 하기 위해는 `EnableFormatSelection` 의 매개 변수는 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> 으로 설정 되어 있어야 `true` VSPackage를 등록 하면 합니다. 이 옵션은 설정 된 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableFormatSelection%2A> 속성을 `true`합니다. <xref:Microsoft.VisualStudio.Package.ViewFilter.CanReformat%2A> 메서드는이 속성의 값을 반환 합니다. True를 반환 하는 경우는 <xref:Microsoft.VisualStudio.Package.ViewFilter> 호출 클래스는 <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A>합니다.  
  
## <a name="implementing-reformatting"></a>다시 포맷 구현

다시 포맷을 구현 하려면에서 클래스를 파생 해야 합니다는 <xref:Microsoft.VisualStudio.Package.Source> 클래스 및 재정의 <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A> 메서드. <xref:Microsoft.VisualStudio.TextManager.Interop.TextSpan> 서식을 지정 하는 범위를 설명 하는 개체 및 <xref:Microsoft.VisualStudio.Package.EditArray> 개체는 범위에서 수행 된 편집을 보유 합니다. 이 범위는 전체 문서 수 있는지 확인 합니다. 그러나 여러를 범위로 변경 될 가능성이 있을 경우 모든 변경 내용을 한 번의 작업에 해독 가능한 이어야 합니다. 이렇게 하려면 모든 변경 내용을 래핑하는 <xref:Microsoft.VisualStudio.Package.CompoundAction> 개체 (이 항목의 "CompoundAction 클래스를 사용 하 여" 섹션 참조).

### <a name="example"></a>예제  

다음 예제에서는 있는지 확인할 공백 하나로 모든 쉽표 뒤 선택 항목에서 쉼표 다음에 탭 또는 줄의 끝에 하지 않는 한 합니다. 후행 공백 줄에는 마지막 쉼표를 삭제 한 후 이 메서드는 호출 하는 방법을 보려면이 항목의 "CompoundAction 클래스를 사용 하 여" 섹션을 참조는 <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A> 메서드.  

```csharp 
using Microsoft.VisualStudio.Package;  
using Microsoft VisualStudio.TextManager.Interop;  
  
namespace MyLanguagePackage  
{  
    class MySource : Source  
    {  
        private void DoFormatting(EditArray mgr, TextSpan span)  
        {  
            // Make sure there is one space after every comma unless followed  
            // by a tab or comma is at end of line.  
            IVsTextLines pBuffer = GetTextLines();  
            if (pBuffer != null)  
            {  
                int    startIndex = span.iStartIndex;  
                int    endIndex   = 0;  
                string line       = "";  
                // Loop over all lines in span  
                for (int i = span.iStartLine; i <= span.iEndLine; i++)  
                {  
                    if (i < span.iEndLine)  
                    {  
                        pBuffer.GetLengthOfLine(i, out endIndex);  
                    }  
                    else  
                    {  
                        endIndex = span.iEndIndex;  
                    }  
                    pBuffer.GetLineText(i, startIndex, i, endIndex, out line);  
  
                    if (line.Length > 0)  
                    {  
                        int index = 0;  
                        // Loop over all commas in line  
                        while ((index = line.IndexOf(',', index)) != -1)  
                        {  
                            int spaceIndex = index + 1;  
                            // Determine how many spaces after comma  
                            while (spaceIndex < line.Length && line[spaceIndex] == ' ')  
                            {  
                                ++spaceIndex;  
                            }  
  
                            int      spaceCount      = spaceIndex - (index + 1);  
                            string   replacementText = " ";  
                            bool     fDoEdit         = true;  
                            TextSpan editTextSpan    = new TextSpan();  
  
                            editTextSpan.iStartLine  = i;  
                            editTextSpan.iEndLine    = i;  
                            editTextSpan.iStartIndex = index + 1;  
  
                            if (spaceIndex == line.Length)  
                            {  
                                if (spaceCount > 0)  
                                {  
                                    // Delete spaces after a comma at end of line  
                                    editTextSpan.iEndIndex = spaceIndex;  
                                    replacementText = "";  
                                }  
                                else  
                                {  
                                    // Otherwise, do not add spaces if comma is  
                                    // at end of line.  
                                    fDoEdit = false;  
                                }  
                            }  
                            else if (spaceCount == 0)  
                            {  
                                if (spaceIndex < line.Length && line[spaceIndex] == '\t')  
                                {  
                                    // Do not insert space if a tab follows  
                                    // a comma.  
                                    fDoEdit = false;  
                                }  
                                else  
                                {  
                                    // No space after comma so add a space.  
                                    editTextSpan.iEndIndex = index + 1;  
                                }  
                            }  
                            else if (spaceCount > 1)  
                            {  
                                // More than one space after comma, replace  
                                // with a single space.  
                                editTextSpan.iEndIndex = spaceIndex;  
                            }  
                            else  
                            {  
                                // Single space after a comma and not at end  
                                // of the line, leave it alone.  
                                fDoEdit = false;  
                            }  
                            if (fDoEdit)  
                            {  
                                // Add edit operation  
                                mgr.Add(new EditSpan(editTextSpan, replacementText));  
                            }  
                            index = spaceIndex;  
                        }  
                    }  
                    startIndex = 0; // All subsequent lines start at 0  
                }  
                // Apply all edits  
                mgr.ApplyEdits();  
            }  
        }  
    }  
}  
```  
  
## <a name="using-the-compoundaction-class"></a>CompoundAction 클래스를 사용 하 여  
 
모든에서 다시 작업을 코드의 한 섹션에서 수행할에서는 단일 작업에서 복구할 수 있어야 합니다. 이 사용 하 여 수행할 수는 <xref:Microsoft.VisualStudio.Package.CompoundAction> 클래스입니다. 이 클래스는 집합이 단일 편집 작업으로 텍스트 버퍼에 대 한 편집 작업을 래핑합니다.  
  
### <a name="example"></a>예제

사용 하는 방법의 예로 <xref:Microsoft.VisualStudio.Package.CompoundAction> 클래스입니다. 예제를 보려면이 항목의 "구현 지원에 대 한 형식 지정" 섹션의 예제를 참조는 `DoFormatting` 메서드.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft VisualStudio.TextManager.Interop;  
  
namespace MyLanguagePackage  
{  
    class MySource : Source  
    {  
        public override void ReformatSpan(EditArray mgr, TextSpan span)  
        {  
            string description = "Reformat code";  
            CompoundAction ca = new CompoundAction(this, description);  
            using (ca)  
            {  
                ca.FlushEditActions();      // Flush any pending edits  
                DoFormatting(mgr, span);    // Format the span  
            }  
        }  
    }  
}  
```  

## <a name="see-also"></a>참고 항목

[레거시 언어 서비스 기능](legacy-language-service-features1.md)