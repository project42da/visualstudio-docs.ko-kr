---
title: "레거시 언어 서비스의 코드를 다시 포맷 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reformatting code, supporting in language services [managed package framework]
- language services [managed package framework], reformatting code
ms.assetid: 08bb3375-8fef-4f4e-9efa-0d7333bab0eb
caps.latest.revision: 12
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
ms.sourcegitcommit: 08d537f003279283509913d5f3d6aaa1bb1c4600
ms.openlocfilehash: d78fb976b3500a657d080634c6a041c218c3f1a1
ms.lasthandoff: 02/22/2017

---
# <a name="reformatting-code-in-a-legacy-language-service"></a>레거시 언어 서비스의 코드를 다시 포맷

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 들여쓰기 및 공백 사용을 정규화 하 여 소스 코드를 재구성 해야 합니다. 이 삽입 또는 공백이 나 탭에서 각 줄의 시작 부분을 제거, 줄 사이 새 줄을 추가 하거나 공간 탭 또는 탭을 공백으로 바꿉니다 포함할 수 있습니다.  
  
>**참고:** 영향을 줄 바꿈 문자를 삭제 또는 삽입 책갈피, 중단점 등의 마커를 줄 수 있지만 공백 또는 탭 추가 및 제거 표식에 영향을 주지 않습니다.  
  
사용자가 선택 하 여 형식을 변경 작업을 시작할 수 **선택 영역 서식** 또는 **문서 서식** 에서 **고급** 메뉴에는 **편집** 메뉴. 코드 조각 또는 특정 문자를 삽입할 때 형식을 변경 작업을 트리거할 수도 있습니다. 예를 들어 C#에 닫는 중괄호를 입력할 때 일치 하는 여는 중괄호 및 닫는 중괄호 사이 있는 모든 없는 경우 적절 한 수준으로 자동으로 들여쓰기
  
때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 보냅니다는 **선택 영역 서식** 또는 **문서 서식** <xref:Microsoft.VisualStudio.Package.ViewFilter>클래스가 <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A> <xref:Microsoft.VisualStudio.Package.Source>클래스</xref:Microsoft.VisualStudio.Package.Source> 에서 메서드</xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A> 를 호출</xref:Microsoft.VisualStudio.Package.ViewFilter> 하는 언어 서비스에 명령 재정의 해야 하는 서식 지정을 지원 하기 위해는 <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A>코드 고유한 서식 지정 메서드 및 공급.</xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A>  
  
## <a name="enabling-support-for-reformatting"></a>다시 포맷 하는 것에 대 한 지원을 사용 하도록 설정  

서식 지정을 지원 하기 위해는 `EnableFormatSelection` 의 매개 변수는 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute>으로 설정 되어 있어야 `true` VSPackage를 등록할 때.</xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> 이 설정의 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableFormatSelection%2A>속성을 `true`.</xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableFormatSelection%2A> <xref:Microsoft.VisualStudio.Package.ViewFilter.CanReformat%2A>메서드는이 속성의 값을 반환 합니다.</xref:Microsoft.VisualStudio.Package.ViewFilter.CanReformat%2A> <xref:Microsoft.VisualStudio.Package.ViewFilter>클래스 호출 <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A>.</xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A> </xref:Microsoft.VisualStudio.Package.ViewFilter> true를 반환 하는 경우  
  
## <a name="implementing-reformatting"></a>다시 포맷 구현

다시 포맷을 구현 하려면에서 클래스를 파생 해야 하는 <xref:Microsoft.VisualStudio.Package.Source>클래스를 재정의 <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A>메서드.</xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A> </xref:Microsoft.VisualStudio.Package.Source> <xref:Microsoft.VisualStudio.TextManager.Interop.TextSpan>개체 형식 및 <xref:Microsoft.VisualStudio.Package.EditArray>개체는 범위에서 편집을 보유</xref:Microsoft.VisualStudio.Package.EditArray> 하는 범위를 설명 합니다.</xref:Microsoft.VisualStudio.TextManager.Interop.TextSpan> 참고가이 범위는 전체 문서를 수 있습니다. 그러나 범위에 대 한 여러 변경 될 가능성이 있을 경우 모든 변경 내용을 한 번의 작업에 해독 가능한 이어야 합니다. 이 위해 모든 변경 내용을 래핑하는 <xref:Microsoft.VisualStudio.Package.CompoundAction>개체 (이 항목의 "CompoundAction 클래스를 사용 하 여" 섹션 참조).</xref:Microsoft.VisualStudio.Package.CompoundAction>

### <a name="example"></a>예제  

다음 예제에서는 있는지 확인할 공백 하나로 모든 쉼표 뒤 선택 항목에서 쉼표 뒤 탭 또는 줄의 끝에 하지 않는 한 합니다. 후행 공백 줄에는 마지막 쉼표를 삭제 한 후 이 메서드는 호출 하는 방법을 알아보려면이 항목의 "CompoundAction 클래스를 사용 하 여" 섹션을 참조는 <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A>메서드.</xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A>  

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
 
코드의 섹션에서 수행 모든 포맷 한 번의 작업에 해독 가능한 이어야 합니다. 이 <xref:Microsoft.VisualStudio.Package.CompoundAction>클래스</xref:Microsoft.VisualStudio.Package.CompoundAction> 를 사용 하 여 수행할 수 있습니다. 이 클래스는 일련의 단일 편집 작업으로 텍스트 버퍼에서 편집 작업을 래핑합니다.  
  
### <a name="example"></a>예제

다음은 <xref:Microsoft.VisualStudio.Package.CompoundAction>클래스</xref:Microsoft.VisualStudio.Package.CompoundAction> 를 사용 하는 방법의 예 이 항목의 예에 "구현 지원에 대 한 서식 지정" 섹션의 예제를 참조는 `DoFormatting` 메서드.  
  
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
