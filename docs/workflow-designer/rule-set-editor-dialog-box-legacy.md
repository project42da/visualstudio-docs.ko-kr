---
title: "규칙 집합 편집기 대화 상자(레거시) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Workflow.Activities.Rules.Design.RuleSetDialog.UI"
helpviewer_keywords: 
  - "규칙 집합 편집기 대화 상자"
ms.assetid: 7cfd5df1-1115-4e5c-9b72-121f39419e83
caps.latest.revision: 7
caps.handback.revision: 7
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# 규칙 집합 편집기 대화 상자(레거시)
이 항목에서는 레거시 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]에서 **규칙 집합 편집기** 대화 상자를 사용하는 방법에 대해 설명합니다.레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.  
  
 **규칙 집합 편집기** 대화 상자는 .rules 파일로 serialize되는 [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019) 규칙 집합을 만들고 수정할 때 사용합니다.  
  
> [!NOTE]
>  **XML 편집기\(인코딩 사용\)**를 사용하여 .rules 파일을 열려면 먼저 해당 워크플로나 활동과 연결된 디자이너 창을 닫아야 합니다.  
  
 **규칙 집합 편집기** 대화 상자에 액세스하는 방법에 대한 자세한 내용은 [방법: PolicyActivity 규칙 집합 만들기\(레거시\)](../workflow-designer/how-to-create-a-policyactivity-rule-set-legacy.md)을 참조하십시오.  
  
> [!WARNING]
>  [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 하는 데 사용되는 레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 규칙 편집기는 멀티 타기팅을 지원하지 않습니다.  
  
 다음 표에서는 **규칙 집합 편집기** 대화 상자의 UI\(사용자 인터페이스\) 요소에 대해 설명합니다.  
  
|UI 요소|설명|  
|-----------|--------|  
|**규칙 추가**|규칙 집합에 새 규칙 정의를 추가합니다.|  
|**삭제**|선택한 규칙을 규칙 집합에서 삭제합니다.|  
|**연결**|규칙 집합에 사용할 전방 연결의 형식을 지정합니다.사용할 수 있는 옵션은 다음과 같습니다.<br /><br /> -   **전체 연결** \- 암시적, 메서드 특성 지정, **Update** 함수를 사용하는 명시적 메커니즘 등 모든 전방 연결 메커니즘을 사용하도록 지정합니다.<br />-   **순차** \- 전방 연결을 사용하지 않도록 지정합니다.<br />-   **명시적 업데이트만** \- **업데이트** 작업에 대해서만 전방 연결을 수행하도록 지정합니다.<br /><br /> 전방 연결에 대한 자세한 내용은 [PolicyActivity 활동 사용](http://go.microsoft.com/fwlink?LinkID=65004)\(영문 페이지일 수 있음\)을 참조하십시오.|  
|**이름**|규칙 집합 목록 열 머리글입니다.규칙 목록을 이름별로 정렬하려면 클릭합니다.|  
|**우선 순위**|규칙 집합 목록 열 머리글입니다.규칙 목록을 우선 순위별로 정렬하려면 클릭합니다.|  
|**재계산**|규칙 집합 목록 열 머리글입니다.규칙 목록을 재계산 형식별로 정렬하려면 클릭합니다.|  
|**규칙 미리 보기**|규칙 집합 목록 열 머리글입니다.규칙 목록을 규칙의 조건 및 작업 미리 보기별로 정렬하려면 클릭합니다.|  
|**이름:**|규칙의 이름을 입력합니다.|  
|**우선 순위:**|규칙의 우선 순위를 입력합니다.기본 우선 순위는 0입니다.|  
|**재계산:**|규칙에 사용할 규칙 재계산의 형식을 지정합니다.사용할 수 있는 옵션은 다음과 같습니다.<br /><br /> -   **항상** \- 필요에 따라 규칙을 재계산합니다.<br />-   **안함** \- 규칙을 재계산하지 않습니다.이 경우에는 규칙이 한 번만 실행됩니다.|  
|**활성**|규칙을 활성화하려면 선택합니다.|  
|**조건:**|규칙 조건을 위한 식을 입력합니다.식 구문에 대한 자세한 내용은 이 페이지의 "조건 및 작업 식 입력" 단원을 참조하십시오.|  
|**ThenActions:**|Then 작업을 위한 식을 입력합니다.식 구문에 대한 자세한 내용은 이 페이지의 "조건 및 작업 식 입력" 단원을 참조하십시오.|  
|**Else 작업:**|Else 작업을 위한 식을 입력합니다.식 구문에 대한 자세한 내용은 이 페이지의 "조건 및 작업 식 입력" 단원을 참조하십시오.|  
|**확인**|규칙 집합을 .rules 파일로 저장하려면 클릭합니다.|  
  
 규칙 집합에 대한 자세한 내용은 [PolicyActivity 활동 사용](http://go.microsoft.com/fwlink?LinkID=65004)\(영문 페이지일 수 있음\)을 참조하십시오.  
  
## 조건 및 작업 식 입력  
 **규칙 집합 편집기** 대화 상자의 각 텍스트 상자에 조건 및 Then 작업과 Else 작업의 식을 텍스트로 입력할 수 있습니다.**this.**를 편집기에 입력하여 워크플로에 사용된 필드, 속성 및 메서드를 IntelliSense 형식의 메뉴를 사용하여 참조할 수 있습니다.또는 워크플로 멤버 이름을 직접 입력할 수도 있습니다.클래스 이름 다음에 메서드 이름을 입력하여 정적 메서드를 참조 형식으로 호출할 수 있습니다.  
  
 AND, OR, NOT 등의 논리 연산자를 조건에 추가할 수 있습니다.조건자를 추가할 수도 있습니다.조건자는 이항 연산자 한 개와 피연산자 두 개로 이루어집니다.지원되는 이항 연산자는 \=\=, \>, \<, \>\= 및 \<\=입니다.지원되는 피연산자는 상수 값, 산술 함수 및 범위 Public 멤버입니다.  
  
 비교 형식을 지정하고 **null** 또는 빈 문자열과 비교할 수 있습니다.`this.Address.State == "WA"`와 같이 복합 형식을 포함하는 변수에서 멤버 호출을 중첩시킬 수 있습니다.  
  
 식은 다음과 같은 연산자를 지원합니다.  
  
-   관계형 연산자: \=\=, \=, \!\=  
  
-   비교 연산자: \<, \<\=, \>, \>\=  
  
-   산술 연산자: \+, \- , \*, \/, MOD  
  
-   논리 연산자: AND, &&, OR, &#124;&#124;, NOT, \!  
  
-   비트 연산자: &, &#124;  
  
 식 연산자 우선 순위는 C\# 연산자 우선 순위 규칙을 따릅니다.  
  
 조건에 대한 자세한 내용은 [Using Conditions in Workflows](http://msdn.microsoft.com/ko-kr/541211f5-d382-4810-894f-71f00b34fa77)을 참조하십시오.  
  
### Halt 및 Update 함수  
 **ThenActions:** 및 **Else 작업:** 식은 **Halt** 및 **Update** 함수를 지원합니다.**Halt** 함수를 사용하려면 **Halt**를 **ThenAction:** 또는 **Else 작업:** 텍스트 상자에 입력합니다.**Halt** 작업을 수행하면 규칙 집합 실행이 즉시 중지되고 호출 코드에 대한 제어로 되돌아갑니다.**Update** 함수를 전방 연결과 함께 사용할 수 있습니다.  
  
 **Update** 문은 편집기에서 두 가지 형태 중 하나로 표현할 수 있습니다. 두 형태 모두 다음 예에서 소개합니다.  
  
```  
Update(this.Address.State)  
Update("this/Address/State")  
```  
  
 전방 연결과 함께 **Update** 사용에 대한 자세한 내용은 [PolicyActivity 활동 사용](http://go.microsoft.com/fwlink?LinkID=65004)\(영문 페이지일 수 있음\)을 참조하십시오.  
  
## 참고 항목  
 [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)   
 [규칙 집합 선택 대화 상자\(레거시\)](../workflow-designer/select-rule-set-dialog-box-legacy.md)   
 [PolicyActivity 활동 사용](http://go.microsoft.com/fwlink?LinkID=65004)   
 [워크플로에서 조건 사용](http://go.microsoft.com/fwlink?LinkID=65009)