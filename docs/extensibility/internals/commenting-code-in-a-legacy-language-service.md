---
title: "레거시 언어 서비스의 코드를 주석 달기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "언어 서비스 [관리 되는 패키지 프레임 워크]에서 지 원하는 메모"
  - "코드 주석 언어 서비스 [관리 되는 패키지 프레임 워크]"
ms.assetid: 9600d6f0-e2b6-4fe0-b935-fb32affb97a4
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# 레거시 언어 서비스의 코드를 주석 달기
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로그래밍 언어는 일반적으로 주석을 추가 하거나 코드를 주석 처리 하는 방법을 제공 합니다.  주석을 코드에 대 한 추가 정보를 제공 하지만 컴파일 또는 해석 시 무시 되는 텍스트의 섹션입니다.  
  
 주석 달기 및 추가 설명을 제거 선택한 텍스트에 대 한 지원을 제공 하는 패키지 관리 프레임 워크 \(MPF\) 클래스입니다.  
  
## 메모 스타일  
 메모의 두 가지 일반 스타일입니다.  
  
1.  한 줄에 주석이 있는 줄 주석입니다.  
  
2.  여러 줄 주석을 포함할 수 있습니다 어디 블록 주석입니다.  
  
 일반적으로 줄 주석 시작 문자 \(또는 문자\) 블록 주석 하면서 시작과 끝 문자 있습니다.  예를 들어, C\#에서 줄 주석 시작 \/ \/, 및 시작 블록 주석 \/ \* 대 한 \* \/.  
  
 사용자가 명령을 선택할 때  **주석 선택** 에서  **편집** \-\>  **고급** 입니다 메뉴에서 명령을 전달 하는 <xref:Microsoft.VisualStudio.Package.Source.CommentSpan%2A> 메서드는 <xref:Microsoft.VisualStudio.Package.Source> 클래스입니다.  사용자가 명령을 선택할 때  **선택 영역의 주석 처리 제거**, 명령을 전달 되는 <xref:Microsoft.VisualStudio.Package.Source.UncommentSpan%2A> 메서드.  
  
## 코드 주석을 지원합니다.  
 사용자 언어 서비스 지원 코드 주석으로 수 있습니다는 `EnableCommenting` 의 매개 변수 이름은 해당 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> .  이 설정의 <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCommenting%2A> 속성에는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> 클래스.  언어 servicce 기능을 설정 하는 방법에 대 한 자세한 내용은 참조 하십시오. [언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md)\).  
  
 또한 재정의 해야는 <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> 메서드가 반환 하는 <xref:Microsoft.VisualStudio.Package.CommentInfo> 구조 주석 문자 언어와.  C\#\-스타일 줄 주석 문자는 기본입니다.  
  
### 예제  
 다음은 구현 예를 <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> 메서드.  
  
```c#  
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
  
## 참고 항목  
 [레거시 언어 서비스 기능](../../extensibility/internals/legacy-language-service-features1.md)   
 [언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md)