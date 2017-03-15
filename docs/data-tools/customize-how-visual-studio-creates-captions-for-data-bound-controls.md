---
title: "방법: Visual Studio에서 데이터 바인딩된 컨트롤에 대한 캡션을 만드는 방식 사용자 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "캡션, 데이터 바인딩"
  - "데이터 소스 창, 레이블 캡션"
  - "레이블 캡션, 데이터 소스 창"
  - "스마트 캡션"
ms.assetid: 6d4d15f8-4d78-42fd-af64-779ae98d62c8
caps.latest.revision: 12
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: Visual Studio에서 데이터 바인딩된 컨트롤에 대한 캡션을 만드는 방식 사용자 지정
[데이터 소스 창](../Topic/Data%20Sources%20Window.md)에서 Windows Forms Designer로 항목을 끌어 놓을 때 특별히 고려해야 할 사항은 두 개 이상의 단어가 함께 연결된 경우 캡션 레이블의 열 이름은 보다 읽기 쉬운 문자열로 서식이 다시 지정된다는 것입니다.  **HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\8.0\\Data Designers** 레지스트리 키의 **SmartCaptionExpression**, **SmartCaptionReplacement** 및 **SmartCaptionSuffix** 값을 설정하여 이러한 레이블을 만드는 방식을 사용자 지정할 수 있습니다.  
  
> [!NOTE]
>  이 레지스트리 키는 사용자가 만들기 전에는 존재하지 않습니다.  
  
 스마트 캡션은 **SmartCaptionExpression**의 값에 입력된 정규식으로 제어됩니다.  **Data Designers** 레지스트리 키를 추가하면 캡션 레이블을 제어하는 기본 정규식이 재정의됩니다.  정규식에 대한 자세한 내용은 [Visual Studio에서 정규식 사용](../ide/using-regular-expressions-in-visual-studio.md)을 참조하십시오.  
  
 다음 표에서는 캡션 레이블을 제어하는 레지스트리 값에 대해 설명합니다.  
  
|레지스트리 항목|설명|  
|--------------|--------|  
|SmartCaptionExpression|패턴을 일치시키는 데 사용되는 정규식입니다.|  
|SmartCaptionReplacement|**SmartCaptionExpression**에 일치하는 그룹을 표시하는 형식입니다.|  
|SmartCaptionSuffix|캡션 끝에 추가할 선택적 문자열입니다.|  
  
 다음 표에서는 이러한 레지스트리 값에 대한 내부 기본 설정을 보여 줍니다.  
  
|항목|기본값|설명|  
|--------|---------|--------|  
|**SmartCaptionExpression**|\(\\\\p{Ll}\)\(\\\\p{Lu}\)&#124;\_\+|대문자나 밑줄이 뒤에 나오는 소문자를 찾습니다.|  
|**SmartCaptionReplacement**|$1 $2|$1은 식의 첫째 괄호에 일치하는 문자를 나타내고 $2는 둘째 괄호에 일치하는 문자를 나타냅니다.  첫째 일치, 공백, 둘째 일치순으로 대체됩니다.|  
|**SmartCaptionSuffix**|:|반환된 문자열에 추가되는 문자를 나타냅니다.  예를 들어, 캡션이 `Company Name`인 경우 접미사가 추가되어 `Company Name:`이 됩니다.|  
  
> [!CAUTION]
>  레지스트리 편집기에서 작업을 수행할 때는 항상 주의해야 합니다.  레지스트리는 편집하기 전에 백업하십시오.  레지스트리 편집기를 잘못 사용하면 심각한 문제가 발생하여 운영 체제를 다시 설치해야 할 수도 있습니다.  Microsoft는 레지스트리 편집기를 잘못 사용하여 발생한 문제에 대한 해결을 보증하지 않습니다.  레지스트리 편집기를 사용할 때는 주의하십시오.  
>   
>  [고급 사용자를 위한 Windows 레지스트리 정보](http://support.microsoft.com/default.aspx?scid=kb;en-us;256986)\(http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;256986\) 기술 자료 문서에는 레지스트리의 백업, 편집 및 복원에 대한 지침이 들어 있습니다.  
  
### 데이터 소스 창의 스마트 캡션 동작을 수정하려면  
  
1.  **시작**, **실행**을 차례로 클릭하여 명령 창을 엽니다.  
  
2.  **실행** 대화 상자에 `regedit`를 입력하고 **확인**을 클릭합니다.  
  
3.  **HKEY\_CURRENT\_USER** 노드를 확장합니다.  
  
4.  **Software** 노드를 확장합니다.  
  
5.  **Microsoft** 노드를 확장합니다.  
  
6.  **VisualStudio** 노드를 확장합니다.  
  
7.  **10.0** 노드를 마우스 오른쪽 단추로 클릭하고 `Data Designers`라는 이름의 새 **키**를 만듭니다.  
  
8.  **Data Designers** 노드를 마우스 오른쪽 단추로 클릭하고 `SmartCaptionExpression`이라는 이름의 새 **문자열 값**을 만듭니다.  
  
9. **Data Designers** 노드를 마우스 오른쪽 단추로 클릭하고 `SmartCaptionReplacement`라는 이름의 새 **문자열 값**을 만듭니다.  
  
10. **Data Designers** 노드를 마우스 오른쪽 단추로 클릭하고 `SmartCaptionSuffix`라는 이름의 새 **문자열 값**을 만듭니다.  
  
11. **SmartCaptionExpression** 항목을 마우스 오른쪽 단추로 클릭하고 **수정**을 선택합니다.  
  
12. **데이터 소스** 창에서 사용할 정규식을 입력합니다.  
  
13. **SmartCaptionReplacement** 항목을 마우스 오른쪽 단추로 클릭하고 **수정**을 선택합니다.  
  
14. 정규식에 일치하는 패턴을 표시할 방식으로 서식이 지정된 문자열을 입력합니다.  
  
15. **SmartCaptionSuffix** 항목을 마우스 오른쪽 단추로 클릭하고 **수정**을 선택합니다.  
  
16. 캡션 끝에 표시하려는 문자를 입력합니다.  
  
     다음에 **데이터 소스** 창에서 항목을 끌면 제공된 새 레지스트리 값을 사용하여 캡션 레이블이 만들어집니다.  
  
### 스마트 캡션 기능을 해제하려면  
  
1.  **시작**, **실행**을 차례로 클릭하여 명령 창을 엽니다.  
  
2.  **실행** 대화 상자에 `regedit`를 입력하고 **확인**을 클릭합니다.  
  
3.  **HKEY\_CURRENT\_USER** 노드를 확장합니다.  
  
4.  **Software** 노드를 확장합니다.  
  
5.  **Microsoft** 노드를 확장합니다.  
  
6.  **VisualStudio** 노드를 확장합니다.  
  
7.  **10.0** 노드를 마우스 오른쪽 단추로 클릭하고 `Data Designers`라는 이름의 새 **키**를 만듭니다.  
  
8.  **Data Designers** 노드를 마우스 오른쪽 단추로 클릭하고 `SmartCaptionExpression`이라는 이름의 새 **문자열 값**을 만듭니다.  
  
9. **Data Designers** 노드를 마우스 오른쪽 단추로 클릭하고 `SmartCaptionReplacement`라는 이름의 새 **문자열 값**을 만듭니다.  
  
10. **Data Designers** 노드를 마우스 오른쪽 단추로 클릭하고 `SmartCaptionSuffix`라는 이름의 새 **문자열 값**을 만듭니다.  
  
11. **SmartCaptionExpression** 항목을 마우스 오른쪽 단추로 클릭하고 **수정**을 선택합니다.  
  
12. 값에 `(.*)`를 입력합니다.  이렇게 하면 전체 문자열을 일치시킵니다.  
  
13. **SmartCaptionReplacement** 항목을 마우스 오른쪽 단추로 클릭하고 **수정**을 선택합니다.  
  
14. 값에 `$1`을 입력합니다.  이렇게 하면 해당 문자열이 일치하는 값과 대체되고, 이때 일치하는 값은 전체 문자열이므로 문자열이 변경되지 않습니다.  
  
     다음에 **데이터 소스** 창에서 항목을 끌면 수정되지 않은 캡션을 사용하여 캡션 레이블이 만들어집니다.  
  
## 참고 항목  
 [.NET Framework 정규식](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)