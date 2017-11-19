---
title: "레거시 언어 서비스의 코드를 주석 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- comments, supporting in language services [managed package framework]
- language services [managed package framework], commenting code
ms.assetid: 9600d6f0-e2b6-4fe0-b935-fb32affb97a4
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8952612c9502704f79410461d29ca8ab87fa3ee4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="commenting-code-in-a-legacy-language-service"></a>레거시 언어 서비스의 코드를 주석 달기
프로그래밍 언어에는 일반적으로 코드를 주석 처리 하거나 주석을 달 수 있는 방법을 제공 합니다. 주석을 코드에 대 한 추가 정보를 제공 하지만 컴파일 또는 해석 하는 동안 무시 하는 텍스트의 섹션입니다.  
  
 관리 되는 패키지 프레임 워크 (MPF) 클래스는 주석 및 주석 처리를 제거 선택한 텍스트에 대 한 지원을 제공합니다.  
  
## <a name="comment-styles"></a>주석 스타일  
 설명의 두 가지 일반 스타일 가지가 있습니다.  
  
1.  한 줄에 주석을 인 줄 주석입니다.  
  
2.  블록 주석, 주석 여러 줄을 포함할 수 있습니다.  
  
 일반적으로 줄으로 된 주석을 시작 문자 (또는 문자), 블록 주석이 하는 동안 시작 및 끝을 모두 자이 하를 가집니다. 예를 들어 C#에서는 한 줄으로 된 주석으로 시작 / /, 블록 주석으로 시작 하 고 / * 끝나는 \*/ 합니다.  
  
 사용자가 명령을 선택할 때 **주석 선택** 에서 **편집** -> **고급** 메뉴 명령에 라우팅 된다고는 <xref:Microsoft.VisualStudio.Package.Source.CommentSpan%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Package.Source> 클래스입니다. 사용자가 명령을 선택할 때 **주석 처리 제거 선택**, 명령에 전달 되는 <xref:Microsoft.VisualStudio.Package.Source.UncommentSpan%2A> 메서드.  
  
## <a name="supporting-code-comments"></a>코드 주석 지원  
 언어 서비스 지원 코드 설명을 방법으로 사용할 수 있습니다는 `EnableCommenting` 명명 된의 매개 변수는 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> 합니다. 이 설정의 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCommenting%2A> 의 속성은 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> 클래스. 언어 servicce 기능을 설정 하는 방법에 대 한 자세한 내용은 참조 [레거시 언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md)).  
  
 도 재정의 해야 합니다는 <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> 반환 하는 메서드는 <xref:Microsoft.VisualStudio.Package.CommentInfo> 주석 문자 언어에 대 한 포함 된 구조입니다. C#-스타일 줄 주석 문자는 기본값입니다.  
  
### <a name="example"></a>예제  
 다음의 예제 구현은는 <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> 메서드.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
  
namespace MyLanguagePackage  
{  
    class MySource : Source  
    {  
        public override CommentInfo GetCommentFormat() {  
            CommentInfo info = new CommentInfo();  
            info.LineStart       = "//";  
            info.BlockStart      = "/*";  
            info.BlockEnd        = "*/";  
            info.UseLineComments = true;  
            return info;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [레거시 언어 서비스 기능](../../extensibility/internals/legacy-language-service-features1.md)   
 [레거시 언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md)