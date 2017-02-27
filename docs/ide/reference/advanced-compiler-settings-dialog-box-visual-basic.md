---
title: "고급 컴파일러 설정 대화 상자(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.ProjectPropertiesAdvancedCompile"
helpviewer_keywords: 
  - "고급 컴파일러 설정 대화 상자"
ms.assetid: 1f81133a-293f-4dba-bc1c-8baafb01d857
caps.latest.revision: 46
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 46
---
# 고급 컴파일러 설정 대화 상자(Visual Basic)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

**프로젝트 디자이너**의 **고급 컴파일러 설정** 대화 상자를 사용하여 프로젝트의 고급 빌드 구성 속성을 지정할 수 있습니다.  이 대화 상자는 Visual Basic 프로젝트에만 적용됩니다.  
  
### 이 대화 상자에 액세스하려면  
  
1.  **솔루션 탐색기**, 프로젝트 노드를 선택 \(않습니다는  **솔루션** 노드\).  
  
2.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  **프로젝트 디자이너**가 나타나면 **컴파일** 탭을 클릭합니다.  
  
3.  [프로젝트 디자이너, 컴파일 페이지\(Visual Basic\)](../../ide/reference/compile-page-project-designer-visual-basic.md)에서 **구성** 및 **플랫폼**을 선택합니다.  단순화된 빌드 구성에서는 **구성** 및 **플랫폼** 목록이 표시되지 않습니다.  자세한 내용은 [Debug and Release Project Configurations](http://msdn.microsoft.com/ko-kr/0440b300-0614-4511-901a-105b771b236e)을 참조하십시오.  
  
4.  **고급 컴파일 옵션**을 클릭합니다.  
  
 [!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]  
  
## 최적화  
 다음 옵션에서는 최적화를 지정하여 경우에 따라 프로그램 파일을 더 작게 만들거나 프로그램을 더 빠르게 실행하거나 또는 빌드 프로세스를 가속화할 수 있도록 합니다.  
  
 **정수 오버플로 검사 해제**  
 기본적으로 정수 오버플로 검사를 사용 하려면이 확인란을 선택 합니다 지워집니다.  정수 오버플로 검사를 제거 하려면이 확인란을 선택 합니다.  이 확인란을 선택 하면 정수 계산이 빠를 수 있습니다.  그러나 오버플로 검사 및 데이터 형식 용량이 오버플로 제거 하면 오류가 발생 하지 않고 잘못 된 결과 저장 되어 있습니다.  
  
 오버플로 조건을 검사 하는 정수 연산 오버플로는 <xref:System.OverflowException> 예외가 throw 됩니다.  작업 오버플로 정수 오버플로 조건을 검사 하지 않으면 예외를 throw 하지 않습니다.  
  
 **최적화 사용**  
 기본적으로 컴파일러 최적화를 사용하지 않도록 이 확인란은 선택되어 있지 않습니다.  컴파일러 최적화를 사용하려면 이 확인란을 선택합니다.  컴파일러 최적화는 출력 파일을 작고 빠르고 효율적이 되도록 만듭니다.  그러나 최적화 코드 오는 출력 파일에 있으므로,, 컴파일러 최적화 디버깅 어려울 수 있습니다.  
  
 **DLL 기준 주소**  
 이 텍스트 상자는 기본 DLL 기준 주소를 16진수 형식으로 표시합니다.  클래스 라이브러리 및 컨트롤 라이브러리 프로젝트에서 이 텍스트 상자를 사용하면 DLL을 만들 때 사용할 기준 주소를 지정할 수 있습니다.  
  
 **디버그 정보 생성**  
 목록에서 **None**, **Full** 또는 **pdb\-only**를 선택합니다.  **None**을 지정하면 디버깅 정보가 생성되지 않습니다.  **Full**을 지정하면 전체 디버깅 정보가 생성되고, **pdb\-only**를 지정하면 PDB 디버깅 정보만 생성됩니다.  기본적으로 이 옵션은 **Full**로 설정되어 있습니다.  
  
## 컴파일 상수  
 조건부 컴파일 상수 있는 사용에 유사한 효과  [\#Const](/dotnet/visual-basic/language-reference/directives/const-directive) 전처리기 지시문은 소스 파일에서 정의 된 상수는 공용이 고 프로젝트의 모든 파일에 적용 된다는.  조건부 컴파일 상수와 함께 사용할 수 있는  [\#If...Then... \#Else](/dotnet/visual-basic/language-reference/directives/if-then-else-directives) 지시문 소스 파일을 조건부로 컴파일할 수 있습니다.  자세한 내용은 [Conditional Compilation](/dotnet/visual-basic/programming-guide/program-structure/conditional-compilation)를 참조하십시오.  
  
 **DEBUG 상수 정의**  
 기본적으로 이 확인란은 선택되어 있으며 DEBUG 상수가 설정되도록 지정합니다.  
  
 **TRACE 상수 정의**  
 기본적으로 이 확인란은 선택되어 있으며 TRACE 상수가 설정되도록 지정합니다.  
  
 **사용자 지정 상수**  
 이 텍스트 상자에 응용 프로그램에 대한 사용자 지정 상수를 입력합니다.  Name1\="Value1",Name2\="Value2",Name3\="Value3" 형식을 사용하여 각 항목을 쉼표로 구분하여 입력해야 합니다.  
  
## 기타 설정  
 **Serialization 어셈블리 생성**  
 이 설정은 컴파일러가 XML serialization 어셈블리를 만들지 여부를 지정합니다.  Serialization 어셈블리를 사용하면 코드에서 형식을 serialize하기 위해 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용한 경우 해당 클래스의 시작 성능을 향상시킬 수 있습니다.  기본적으로 이 옵션은 **자동**으로 설정됩니다. 이 경우 코드에서 형식을 XML로 인코딩하기 위해 <xref:System.Xml.Serialization.XmlSerializer>를 사용한 경우에만 Serialization 어셈블리가 생성됩니다.  이 옵션을 **해제**로 설정하면 코드에서 <xref:System.Xml.Serialization.XmlSerializer>를 사용하는지에 관계없이 Serialization 어셈블리가 생성되지 않습니다.  이 옵션을 **설정**으로 지정하면 항상 Serialization 어셈블리가 생성됩니다.  Serialization 어셈블리의 이름은 `TypeName`.XmlSerializers.dll입니다.  
  
## 참고 항목  
 [프로젝트 디자이너, 컴파일 페이지\(Visual Basic\)](../../ide/reference/compile-page-project-designer-visual-basic.md)