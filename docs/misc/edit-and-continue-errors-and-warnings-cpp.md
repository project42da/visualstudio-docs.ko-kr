---
title: "편집하며 계속하기의 오류 및 경고(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ENC2001"
  - "ENC1006"
  - "ENC2008"
  - "ENC1009"
  - "ENC1002"
  - "ENC2002"
  - "ENC1011"
  - "ENC1003"
  - "ENC1004"
  - "ENC1008"
  - "ENC1013"
  - "ENC2005"
  - "ENC1010"
  - "ENC2004"
  - "ENC1007"
  - "ENC1005"
  - "ENC2006"
  - "ENC1001"
  - "ENC2007"
  - "ENC2003"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "편집하며 계속하기[C++], 오류 및 경고"
  - "오류[C++], 편집하며 계속하기"
  - "오류[디버거], 편집하며 계속하기"
ms.assetid: b5c5e25c-7ca4-4ca9-b91e-e8882de44dae
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "susanno"
manager: "douge"
---
# 편집하며 계속하기의 오류 및 경고(C++)
[!INCLUDE[cpp_current_short](../misc/includes/cpp_current_short_md.md)] 편집하며 계속하기를 사용하면 중단 모드에서 프로그램 실행을 중지하고 실행 코드를 변경한 다음 새로 통합된 변경 내용을 사용하여 프로그램 실행을 다시 시작할 수 있습니다.  
  
 클래스의 공용 구조체에 영향을 주는 선언 코드 편집은 일반적으로 금지되며, 클래스 내의 private 선언, 속성 본문 또는 메서드에 대한 일부 편집이 허용되지 않습니다.  편집하며 계속하기에서는 편집할 수 없는 코드를 가능한 경우 항상 연한 회색으로 표시하고 오류 메시지를 표시합니다.  [!INCLUDE[cpp_current_short](../misc/includes/cpp_current_short_md.md)]의 편집하며 계속하기에서 지원되지 않는 편집에 대한 자세한 내용은 [편집하며 계속하기\(Visual C\+\+\)](../debugger/edit-and-continue-visual-cpp.md)를 참조하십시오.  
  
 편집하며 계속하기 오류 및 경고는 다음 방법 중 하나로 해결할 수 있습니다.  
  
|해결|오류 및 경고 메시지 번호|  
|--------|--------------------|  
|디버깅을 중지하고 변경 내용을 다시 적용한 다음 디버깅을 다시 시작합니다.|1001, 1002, 1003, 1004, 1005, 1006, 1007, 1008, 1010, 1013, 2003, 2005 이 범주의 오류 및 경고 메시지 목록을 보려면 [디버깅 다시 시작 메시지](../misc/edit-and-continue-errors-and-warnings-cpp.md#BKMK_RestartDebuggingMessages)를 참조하십시오.|  
|**편집** 메뉴에서 **실행 취소**를 선택한 다음 변경되지 않은 코드로 디버깅을 계속합니다.<br /><br /> \-또는\-<br /><br /> 디버깅을 중지하고 변경 내용을 다시 적용한 다음 디버깅을 다시 시작합니다.|1009, 1011 이 범주의 오류 및 경고 메시지 목록을 보려면 [실행 취소 또는 중지 메시지](../misc/edit-and-continue-errors-and-warnings-cpp.md#BKMK_UndoOrStopMessages)를 참조하십시오.|  
|디버깅을 계속합니다.  변경 내용은 코드가 처음으로 적중될 때 무시되지만 이후 호출에서 적용됩니다.|2001, 2002, 2004.  이 범주의 오류 및 경고 메시지 목록을 보려면 [다음 호출에서 적용 메시지](../misc/edit-and-continue-errors-and-warnings-cpp.md#BKMK_ApplyAtNextCallMessages)를 참조하십시오.|  
|중단점을 다시 설정하거나 현재 버전의 [!INCLUDE[cpp_current_short](../misc/includes/cpp_current_short_md.md)]를 사용하여 모듈을 다시 빌드하는 등의 다른 작업을 수행합니다.|2007, 2008.  이 범주의 오류 및 경고 메시지 목록을 보려면 [다른 작업 필요 메시지](../misc/edit-and-continue-errors-and-warnings-cpp.md#BKMK_OtherActionRequiredMessages)를 참조하십시오.|  
  
##  <a name="BKMK_RestartDebuggingMessages"></a> 디버깅 다시 시작 메시지  
 다음 오류 메시지는 현재 디버깅 세션을 중지하고 편집한 내용을 다시 적용한 다음 디버깅 세션을 다시 시작하여 해결해야 합니다.  
  
|||  
|-|-|  
|1001|기호 썽크를 업데이트할 수 없습니다. *symbol*\(loc: *location*, 썽크: *address*\)|  
|1002|데이터 기호가 변경되었습니다. 기호\(*symbol*\)|  
|1003|새 함수의 썽크를 매핑할 수 없습니다. *function*|  
|1004|형식 압축을 위한 PDB를 열 수 없습니다. *pdb*\(pdb\)|  
|1005|기호가 이름이 바뀌었거나, 제거되었거나, 수정되었습니다. *symbol*|  
|1006|전역 또는 정적 변수가 추가되었거나, 이름이 바뀌었거나, 제거되었거나 또는 데이터 형식이나 초기화가 변경되었습니다. *symbol*\(참조: *module*\)|  
|1007|정의하지 않은 기호입니다. *symbol*\(참조: *module*\)|  
|1008|편집 중에 로드된 개체에 필요한 런타임 초기화를 수행할 수 없습니다. *module*|  
|1010|정적 또는 전역 변수가 추가되었습니다. *variable referenced in file*|  
|1013|코드 변경 내용을 적용하는 데 메모리가 부족합니다.|  
|2003|코드 위치를 변경하면 예외 처리 또는 변수 소멸 오류가 발생할 수 있습니다. *function*|  
|2005|새 소스가 코드에 적용됩니다.  디버거의 줄 번호 정보에 영향을 줄 수 있습니다. 함수\(*function*\)|  
  
##  <a name="BKMK_UndoOrStopMessages"></a> 실행 취소 또는 중지 메시지  
 다음 오류 메시지는 현재 디버깅 세션을 중지하고 편집한 내용을 다시 적용한 다음 디버깅 세션을 다시 시작하여 해결할 수 있습니다.  
  
-   편집 메뉴에서 실행 취소를 클릭합니다.  디버깅을 다시 시작할 수 있지만 편집 내용은 적용되지 않습니다.  
  
     \-또는\-  
  
-   디버깅을 중지하고 편집 내용을 다시 적용한 다음 디버깅을 다시 시작합니다.  
  
|||  
|-|-|  
|1009|정적 또는 전역 변수가 삭제되었습니다. *variable referenced in file*|  
|1011|정적 또는 전역 변수가 변경되었습니다. *variable referenced in file*|  
  
##  <a name="BKMK_ApplyAtNextCallMessages"></a> 다음 호출에서 적용 메시지  
 다음 경고 메시지 중 하나가 표시되면 디버깅 세션을 계속 진행할 수 있습니다.  편집 내용은 편집 후 코드가 처음으로 호출될 때 적용되지 않고 코드에 대한 모든 이후 호출에서 적용됩니다.  
  
|||  
|-|-|  
|2001|변경된 지역 변수나 변수 데이터 형식을 찾을 수 없습니다. 기호\(*symbol*\)|  
|2002|삭제된 변수나 새 지역 변수는 다시 생성하거나 소멸시켜야 합니다. 기호\(*symbol*\)|  
|2004|이미 두 번 이상 정의된 이름을 가진 지역 변수를 추가하거나 제거할 수 없습니다. 기호\(*symbol*\)|  
  
##  <a name="BKMK_OtherActionRequiredMessages"></a> 다른 작업 필요 메시지  
 다음 메시지를 해결하는 데 필요한 작업이 메시지 텍스트 뒤에 설명되어 있습니다.  
  
|||  
|-|-|  
|2007|디스어셈블리 창에 설정된 일부 중단점을 이동할 수 없습니다.<br /><br /> 이 문제를 해결하려면 영향을 받는 중단점을 다시 설정합니다.|  
|2008|*file* 파일\(*module* 모듈에 있음\)의 디버그 기호를 로드할 수 없습니다.<br /><br /> 이 문제를 해결하려면 현재 버전의 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]를 사용하여 지정된 모듈을 다시 빌드합니다.|  
  
## 참고 항목  
 [편집하며 계속하기\(Visual C\+\+\)](../debugger/edit-and-continue-visual-cpp.md)   
 [편집하며 계속하기](../debugger/edit-and-continue.md)