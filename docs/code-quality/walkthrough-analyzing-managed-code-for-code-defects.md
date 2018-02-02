---
title: "코드 오류에 대 한 관리 코드 분석 하는 연습 | Microsoft Docs"
ms.custom: 
ms.date: 01/29/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.topic: article
helpviewer_keywords:
- code analysis [Visual Studio]
- managed code, analyzing
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: e1c708f31d31dd811017015cd37c7e60d49beef9
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="walkthrough-analyzing-managed-code-for-code-defects"></a>연습: 코드에 대 한 관리 코드 분석 오류

이 연습에서는 코드 분석 도구를 사용 하 여 코드 오류에 대 한 관리 되는 프로젝트를 분석할 수 있습니다.

이 연습에서는 Microsoft.NET Framework 디자인 지침 준수에 대 한.NET 관리 되는 코드 어셈블리를 분석 하려면 코드 분석을 사용 하는 과정을 안내 합니다.

## <a name="create-a-class-library"></a>클래스 라이브러리 만들기

### <a name="to-create-a-class-library"></a>클래스 라이브러리를 만들려면

1. 에 **파일** 메뉴 선택 **새로** > **프로젝트...** .

1. 에 **새 프로젝트** 대화 상자에서 **설치 됨** > **Visual C#**를 선택한 후 **클래식 Windows 데스크톱**합니다.

1. 선택 된 **클래스 라이브러리 (.NET Framework)** 서식 파일입니다.

1. 에 **이름** 텍스트 상자에서 **CodeAnalysisManagedDemo** 클릭 하 고 **확인**합니다.

1. 프로젝트가 만들어진 후에 열은 *Class1.cs* 파일입니다.

1. Class1.cs의 기존 텍스트를 다음 코드로 바꿉니다.

   ```csharp
   using System;

   namespace testCode
   {
       public class demo : Exception
       {
           public static void Initialize(int size) { }
           protected static readonly int _item;
           public static int item { get { return _item; } }
       }
   }
   ```

1. Class1.cs 파일을 저장 합니다.

## <a name="analyze-the-project"></a>프로젝트를 분석

### <a name="to-analyze-a-managed-project-for-code-defects"></a>코드 오류에 대 한 관리 되는 프로젝트를 분석 하려면

1. 에 있는 CodeAnalysisManagedDemo 프로젝트 **솔루션 탐색기**합니다.
  
1. **프로젝트** 메뉴에서 **속성**을 클릭합니다.
  
     CodeAnalysisManagedDemo 속성 페이지가 표시 됩니다.
  
1. 선택 된 **코드 분석** 탭 합니다.
  
1. 다음 사항을 확인 **빌드에 코드 분석 사용** 을 선택 합니다.
  
1. **이 규칙 집합 실행** 드롭 다운 목록 **Microsoft 모든 규칙**합니다.
  
1. 에 **파일** 메뉴를 클릭 하 여 **선택한 항목 저장**, 한 다음 속성 페이지를 닫습니다.
  
1. 에 **빌드** 메뉴를 클릭 하 여 **CodeAnalysisManagedDemo 빌드**합니다.
  
    CodeAnalysisManagedDemo 프로젝트 빌드 경고에 표시 되는 **오류 목록** 및 **출력** windows 합니다.

## <a name="correct-the-code-analysis-issues"></a>코드 분석 문제 해결

### <a name="to-correct-code-analysis-rule-violations"></a>코드 분석 규칙 위반을 해결 하려면

1. 에 **보기** 메뉴 선택 **오류 목록**합니다.

    선택한 개발자 프로필에 따라를 가리키도록 할 수 있습니다 **다른 창** 에 **보기** 메뉴를 선택한 후 **오류 목록**합니다.

1. **솔루션 탐색기**, 선택 **모든 파일 표시**합니다.

1. 속성 노드를 확장 한 다음 엽니다는 *AssemblyInfo.cs* 파일입니다.

1. 경고를 해결 하려면 다음 팁을 사용 합니다.

   [CA1014: CLSCompliantAttribute로 어셈블리 표시](../code-quality/ca1014-mark-assemblies-with-clscompliantattribute.md): Microsoft.Design: '데모'는 CLSCompliantAttribute로 표시 해야 하 고 해당 값은 true 여야 합니다.

   1. 코드를 추가 `using System;` AssemblyInfo.cs 파일에 있습니다.

   1. 다음으로 코드를 추가 `[assembly: CLSCompliant(true)]` AssemblyInfo.cs 파일의 끝입니다.

   [CA1032: 표준 예외 생성자를 구현](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design:이 클래스에 다음 생성자를 추가 합니다: 공용 demo(String)

   1. 생성자를 추가 `public demo (String s) : base(s) { }` 클래스 `demo`합니다.

   [CA1032: 표준 예외 생성자를 구현](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design:이 클래스에 다음 생성자를 추가: 공개 데모 (String, 예외)

   1. 생성자를 추가 `public demo (String s, Exception e) : base(s, e) { }` 클래스 `demo`합니다.

   [CA1032: 표준 예외 생성자를 구현](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design:이 클래스에 다음 생성자를 추가: 데모 (SerializationInfo, StreamingContext)를 보호 합니다.

   1. 코드를 추가 `using System.Runtime.Serialization;` Class1.cs 파일의 시작 부분에 있습니다.

   1. 그런 다음 생성자를 추가 합니다.`protected demo (SerializationInfo info, StreamingContext context) : base(info, context) { } to the class demo.`

   [CA1032: 표준 예외 생성자를 구현](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design:이 클래스에 다음 생성자를 추가 합니다: 공용 demo()

   1. 생성자를 추가 `public demo () : base() { }` 클래스 `demo` **합니다.**

   [CA1709: 식별자 표기 해야 올바르게](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming: testCode' 네임 스페이스 이름'의 대/소문자를 'TestCode'로 변경 하 여 해결 합니다.

   1. 네임 스페이스의 대/소문자 변경 `testCode` 를 `TestCode`합니다.

   [CA1709: 식별자 표기 해야 올바르게](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming: 형식 이름 '데모'의 대/소문자를 '데모'로 변경 하 여 해결 합니다.

   1. 멤버의 이름을 변경 `Demo`합니다.

   [CA1709: 식별자 표기 해야 올바르게](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming: 멤버 이름 'item'의 대/소문자를 'Item'로 변경 하 여 해결 합니다.

   1. 멤버의 이름을 변경 `Item`합니다.

   [: Ca1710 식별자에는 올바른 접미사 사용 해야 합니다.](../code-quality/ca1710-identifiers-should-have-correct-suffix.md): Microsoft.Naming: 이름 바꾸기 'testCode.demo' 'Exception'에서 끝나야 합니다.

   1. 클래스 및 해당 생성자의 이름을 변경 `DemoException`합니다.

   [CA2210: 어셈블리 이름을 사용 해야 올바른 강력한](../code-quality/ca2210-assemblies-should-have-valid-strong-names.md): 'CodeAnalysisManagedDemo' 강력한 이름 키로 서명 합니다.

   1. 에 **프로젝트** 메뉴 선택 **CodeAnalysisManagedDemo 속성**합니다.

      프로젝트 속성이 표시 됩니다.

   1. **서명** 탭을 선택합니다.

   1. 선택 된 **어셈블리에 서명** 확인란 합니다.

   1. 에 **강력한 이름 키 파일 선택** 목록에서  **\<새로 만들기 … >**합니다.

      **강력한 이름 키 만들기** 대화 상자가 나타납니다.

   1. 에 **키 파일 이름**, TestKey를 입력 합니다.

   1. 암호를 입력 한 다음 **확인**합니다.

   1. 에 **파일** 메뉴 선택 **선택한 항목 저장**, 한 다음 속성 페이지를 닫습니다.

   [CA2237: ISerializable 형식을 SerializableAttribute로 표시](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md): Microsoft.Usage:이 형식이 ISerializable을 구현 하 '는 데모' 형식으로 [Serializable] 특성을 추가 합니다.

   1. 추가 `[Serializable ()]` 특성을 클래스 `demo`합니다.

   변경을 완료한 후 Class1.cs 파일은 다음과 같습니다.

   ```csharp
   using System;
   using System.Runtime.Serialization;

   namespace TestCode
   {
       [Serializable()]
       public class DemoException : Exception
       {
           public DemoException () : base() { }
           public DemoException(String s) : base(s) { }
           public DemoException(String s, Exception e) : base(s, e) { }
           protected DemoException(SerializationInfo info, StreamingContext context) : base(info, context) { }

           public static void Initialize(int size) { }
           protected static readonly int _item;
           public static int Item { get { return _item; } }
       }
   }
   ```

1. 프로젝트를 다시 빌드합니다.

## <a name="exclude-code-analysis-warnings"></a>코드 분석 경고를 제외 합니다.

### <a name="to-exclude-code-defect-warnings"></a>코드 오류 경고를 제외 하려면

1. 나머지 경고 각각에 대해 다음을 수행합니다.

    1. 경고를 선택는 **오류 목록**합니다.

    1. 마우스 오른쪽 단추 클릭 또는 상황에 맞는 메뉴에서 선택 **표시 안 함** > **억제 (suppression) 파일에서**합니다.

1. 프로젝트를 다시 빌드합니다.

     경고 또는 오류 없이 프로젝트가 빌드됩니다.

## <a name="see-also"></a>참고 항목

[관리 코드에 대 한 코드 분석](../code-quality/code-analysis-for-managed-code-overview.md)