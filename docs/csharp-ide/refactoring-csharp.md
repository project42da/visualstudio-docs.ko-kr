---
title: "Refactoring (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.csharp.refactoring.preview"
  - "vs.csharp.refactoring.issues"
  - "vs.csharp.refactoring.buildwarning"
  - "VS.PreviewChanges"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "refactoring [C#]"
ms.assetid: a39e656a-f81f-4c87-b484-a23168ff1dfc
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Refactoring (C#)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

리팩터링은 코드가 작성된 후 코드의 외부 동작은 변경하지 않고 코드의 내부 구조를 변경하여 코드를 향상시키는 프로세스입니다.  
  
 Visual C\#은 **리팩터링** 메뉴에서 다음 리팩터링 명령을 제공합니다.  
  
-   [메서드 추출 리팩터링\(C\#\)](../csharp-ide/extract-method-refactoring-csharp.md)  
  
-   [이름 바꾸기 리팩터링\(C\#\)](../csharp-ide/rename-refactoring-csharp.md)  
  
-   [Encapsulate Field Refactoring \(C\#\)](../csharp-ide/encapsulate-field-refactoring-csharp.md)  
  
-   [Extract Interface Refactoring \(C\#\)](../csharp-ide/extract-interface-refactoring-csharp.md)  
  
-   [리팩터링 매개 변수 제거\(C\#\)](../csharp-ide/remove-parameters-refactoring-csharp.md)  
  
-   [Reorder Parameters Refactoring \(C\#\)](../csharp-ide/reorder-parameters-refactoring-csharp.md)  
  
## 다중 프로젝트 리팩터링  
 Visual Studio는 동일한 솔루션에 있는 프로젝트에 대한 다중 프로젝트 리팩터링을 지원합니다.  파일에 대한 참조를 수정하는 모든 리팩터링 작업은 언어가 동일한 모든 프로젝트에 대한 해당 참조를 수정합니다.  이것은 프로젝트 간 참조에만 적용됩니다.  예를 들어, 클래스 라이브러리를 참조하는 콘솔 응용 프로그램이 있는 경우 `Rename` 리팩터링 작업을 사용하여 클래스 라이브러리 형식의 이름을 바꾸면 콘솔 응용 프로그램에 있는 클래스 라이브러리 형식에 대한 참조도 업데이트됩니다.  
  
## 변경 내용 미리 보기  
 많은 리팩터링 작업에서는 변경 내용을 커밋하기 전에 코드에 수행된 모든 참조 변경 내용을 검토할 수 있는 기회를 제공합니다.  이러한 리팩터링 작업의 경우 리팩터링 대화 상자에 **참조 변경 내용 미리 보기** 옵션이 나타납니다.  이 옵션을 선택하고 리팩터링 작업을 적용하면 **변경 내용 미리 보기 대화 상자**가 나타납니다.  **변경 내용 미리 보기** 대화 상자에는 두 개의 보기가 있습니다.  아래쪽 보기에는 리팩터링 작업으로 인한 모든 참조 업데이트와 함께 코드가 표시됩니다.  **변경 내용 미리 보기** 대화 상자에서 **취소**를 누르면 리팩터링 작업이 중지되고 코드가 변경되지 않습니다.  
  
## 리팩터링 경고  
 컴파일러가 프로그램을 완전히 이해하지 못하여 리팩터링 엔진이 모든 해당 참조를 업데이트하지 않을 수도 있는 경우 경고 대화 상자가 표시됩니다.  또한 이 경고 대화 상자는 변경 내용을 커밋하기 전에 **변경 내용 미리 보기**에서 코드를 미리 볼 수 있는 기회를 제공합니다.  
  
> [!NOTE]
>  IDE에서 빨간색 물결선으로 표시한 구문 오류가 메서드에 있는 경우 리팩터링 엔진은 해당 메서드 내의 요소에 대한 모든 참조를 업데이트하지 않습니다.  다음 예제는 이 동작을 보여 줍니다.  
  
 기본적으로 참조 변경 내용을 미리 보지 않고 리팩터링 작업을 실행했는데 프로그램에서 컴파일 오류가 발견되면 개발 환경은 이 경고 대화 상자를 표시합니다.  
  
 **참조 변경 내용 미리 보기**가 활성화된 상태에서 리팩터링 작업을 실행했는데 프로그램에서 컴파일 오류가 발견되는 경우 개발 환경은 **리팩터링 경고** 대화 상자를 표시하는 대신 **변경 내용 미리 보기** 대화 상자의 아래쪽에 다음 경고 메시지를 표시합니다.  
  
 **프로젝트 또는 종속 프로젝트 중 하나가 현재 빌드되지 않았습니다.  참조가 업데이트되지 않을 수 있습니다.**  
  
 이 리팩터링 경고는 **참조 변경 내용 미리 보기** 옵션을 제공하는 리팩터링 작업에만 사용될 수 있습니다.  
  
## 오류 무시 리팩터링 및 확인 결과  
 리팩터링은 오류를 무시합니다.  즉, 빌드할 수 없는 프로젝트에서 리팩터링을 수행할 수 있습니다.  하지만 이러한 경우 리팩터링 프로세스에서 모호한 참조를 올바르게 업데이트할 수 없습니다.  
  
 **확인 결과** 대화 상자는 리팩터링 엔진에서 컴파일 오류를 발견하거나 리팩터링 작업으로 인해 코드 참조가 원래 바인딩된 것과 다른 것에 바인딩된다는 사실을 발견하는 경우\(다시 바인딩 문제\) 사용자에게 알릴 수 있습니다.  
  
 확인 결과 기능을 설정하려면 **도구** 메뉴에서 **옵션**을 클릭합니다.  **옵션** 대화 상자에서 **텍스트 편집기**를 확장한 다음 **C\#**을 확장합니다.  **고급**을 클릭하고 **리팩터링 결과 확인** 확인란을 선택합니다.  
  
 **확인 결과** 대화 상자에서는 두 종류의 다시 바인딩 문제 간 차이를 구별합니다.  
  
### 더 이상 이름을 바꾼 기호로 정의되지 않는 참조입니다.  
 참조가 더 이상 이름을 바꾼 기호를 참조하지 않는 경우 이런 종류의 다시 바인딩 문제가 발생합니다.  예를 들어, 다음 코드를 고려하십시오.  
  
```c#  
class Example  
{  
    private int a;  
    public Example(int b)  
    {  
        a = b;  
    }  
}  
```  
  
 리팩터링을 사용하여 이름을 `a`에서 `b`로 바꾸면 이 대화 상자가 나타납니다.  이름을 바꾼 변수 `a`에 대한 참조는 필드에 바인딩되는 대신 생성자로 전달되는 매개 변수에 바인딩됩니다.  
  
### 이름을 바꾼 기호로 정의되는 참조입니다.  
 이름을 바꾼 기호를 참조하지 않았던 참조가 이제는 이름을 바꾼 기호를 참조하는 경우 이런 종류의 다시 바인딩 문제가 발생합니다.  예를 들어, 다음 코드를 고려하십시오.  
  
```c#  
class Example  
{  
    private static void Method(object a) { }  
    private static void OtherMethod(int a) { }  
    static void Main(string[] args)  
    {  
        Method(5);  
    }  
}  
```  
  
 리팩터링을 사용하여 이름을 `OtherMethod`에서 `Method`로 바꾸면 이 대화 상자가 나타납니다.  `Main`의 참조는 이제 `object` 매개 변수를 받는 오버로드된 메서드 대신 `int` 매개 변수를 받는 오버로드된 메서드를 참조합니다.  
  
## 참고 항목  
 [Using the Visual C\# Development Environment](../csharp-ide/using-the-visual-studio-development-environment-for-csharp.md)   
 [방법: C\# 리팩터링 코드 조각 복원](../ide/how-to-restore-csharp-refactoring-snippets.md)