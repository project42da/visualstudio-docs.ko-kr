---
title: "옵션, 텍스트 편집기, C#, 고급 | Microsoft Docs"
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Outlining
- VS.ToolsOptionsPages.Text_Editor.CSharp.Advanced
helpviewer_keywords:
- XML comments
- XML documentation, generating
- outlining options [C#]
- XML documentation, creating
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 5d6cf8b655151e9b07111b6ac6fd64b6ad3c845f
ms.sourcegitcommit: 238cd48787391aa0ed1eb684f3f04e80f7958705
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2018
---
# <a name="options-text-editor-c-advanced"></a>옵션, 텍스트 편집기, C#, 고급

**고급** 옵션을 사용하여 
C#의 편집기 서식, 코드 리팩터링 및 XML 문서 주석에 대한 설정을 수정합니다. 이 옵션 페이지에 액세스하려면 **도구** > **옵션**을 선택한 다음, **텍스트 편집기** > **C#** > **고급**을 선택합니다.

> [!NOTE]
> 표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.

## <a name="analysis"></a>분석

- 전체 솔루션 분석 사용

   열린 코드 파일뿐만 아니라 솔루션의 모든 파일에 대해 코드 분석을 사용할 수 있습니다. 자세한 내용은 [전체 옵션 분석](../../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md)을 참조하세요.

- 외부 프로세스에서 편집기 기능 분석 수행(실험적)

## <a name="using-directives"></a>Using 지시문

- using 정렬 시 ‘System’ 지시문 먼저 배치

- Using 지시문 그룹 구분

- 참조 어셈블리의 형식에 대한 using 제안

- NuGet 패키지의 형식에 대한 using 제안

## <a name="highlighting"></a>강조 표시

- 커서 아래의 기호에 대한 참조 강조

   기호 내부에 커서를 놓거나 기호를 클릭하면 코드 파일에 있는 해당 기호의 모든 인스턴스가 강조 표시됩니다.

- 커서 아래의 관련 키워드 강조

## <a name="outlining"></a>개요

- 개요 모드로 파일 열기

   이 옵션을 선택하면 축소 가능한 코드 블록을 만드는 코드 파일이 자동으로 요약됩니다. 파일이 처음 열리면 #regions 블록 및 비활성 코드 블록이 축소됩니다.

- 프로시저 줄 구분선 표시

- 선언 수준 구문에 대한 개요 표시

- 코드 수준 구문에 대한 개요 표시

- 주석 및 전처리기 영역에 대한 개요 표시

- 정의로 축소할 때 #regions 축소

## <a name="fading"></a>페이딩

- 사용하지 않는 using 페이드 아웃

- 접근할 수 없는 코드 페이드 아웃

## <a name="block-structure-guides"></a>블록 구조 가이드

- 선언 수준 구문에 대한 가이드 표시

- 코드 수준 구문에 대한 가이드 표시

## <a name="editor-help"></a>편집기 도움말

- ///에 대해 XML 문서 주석 생성

   이 옵션을 선택한 경우 `///` 주석 도입부를 입력한 후 XML 문서 주석에 대한 XML 요소를 삽입합니다. XML 문서에 대한 자세한 내용은 [XML 문서 주석(C# 프로그래밍 가이드)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)을 참조하세요.

- /\* \*/ 주석을 작성할 때 새 줄의 시작 부분에 \* 삽입

- 이름 바꾸기 추적 미리 보기 표시

- Enter 키를 누를 때 문자열 리터럴 분할

- 'string.Format' 호출에서 잘못된 자리 표시자 보고

## <a name="extract-method"></a>메서드 추출

- 사용자 지정 구조체에 ref 또는 out 추가 안 함

## <a name="implement-interface-or-abstract-class"></a>인터페이스 또는 추상 클래스 구현

- 속성, 이벤트 및 메서드를 삽입할 때 이들을 같은 종류의 다른 멤버와 함께 또는 끝에 배치

- 속성을 생성할 때 throw 속성 선호 또는 자동 속성 선호

## <a name="see-also"></a>참고 항목

[방법: 문서 생성에 대한 XML 주석 삽입](../../ide/reference/generate-xml-documentation-comments.md)  
[XML 문서 주석(C# 프로그래밍 가이드)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)  
[XML 주석과 함께 코드 문서화(C# 가이드)](/dotnet/csharp/codedoc)  
[언어별 편집기 옵션 설정](../../ide/reference/setting-language-specific-editor-options.md)  
[C# IntelliSense](../../ide/visual-csharp-intellisense.md)