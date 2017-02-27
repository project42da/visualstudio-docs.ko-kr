---
title: "방법: PolicyActivity 규칙 집합 만들기(레거시) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "PolicyActivity 활동, 규칙 집합 만들기"
  - "PolicyActivity 활동, 규칙 집합 선택"
  - "규칙 집합 편집기 대화 상자"
  - "규칙 집합, PolicyActivity에 대해 만들기"
  - "규칙 집합 선택 대화 상자"
ms.assetid: f272489d-3342-4511-8b59-6a0fd7a42d70
caps.latest.revision: 4
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# 방법: PolicyActivity 규칙 집합 만들기(레거시)
이 항목에서는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 하는 레거시 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]를 사용하여 정책 활동 규칙 집합을 만드는 방법에 대해 설명합니다.  
  
 **도구 상자**에서 워크플로 디자인 화면으로 **정책** 활동 항목을 끌어 온 후에는 [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019) 활동을 위해 기존 규칙을 선택하거나 새 규칙 집합을 만들 수 있습니다.기존 규칙 집합을 선택하려면 [규칙 집합 선택 대화 상자\(레거시\)](../workflow-designer/select-rule-set-dialog-box-legacy.md)를 사용하고 규칙 집합을 만들려면 [규칙 집합 편집기 대화 상자\(레거시\)](../workflow-designer/rule-set-editor-dialog-box-legacy.md)를 사용합니다.  
  
> [!NOTE]
>  워크플로 디자인 화면에 있는 [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)\(영문 페이지일 수 있음\) 활동을 두 번 클릭하여 [규칙 집합 편집기 대화 상자\(레거시\)](../workflow-designer/rule-set-editor-dialog-box-legacy.md) 대화 상자를 직접 열 수 있습니다.  
  
### PolicyActivity 활동의 규칙 집합을 선택하거나 만들려면  
  
1.  [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)\(영문 페이지일 수 있음\)를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭하여 **속성** 창을 엽니다.  
  
2.  **RuleSetReference** 속성을 클릭합니다.  
  
3.  다음 작업 중 하나를 수행합니다.  
  
    -   **RuleSetReference** 줄임표 **\[…\]**를 클릭한 다음 [규칙 집합 선택 대화 상자\(레거시\)](../workflow-designer/select-rule-set-dialog-box-legacy.md)에서 기존 규칙 집합을 선택합니다.10단계로 이동합니다.  
  
         \- 또는 \-  
  
    -   규칙 집합의 이름을 입력합니다.**RuleSetReference** 줄임표 **\[…\]**를 클릭한 다음 [규칙 집합 선택 대화 상자\(레거시\)](../workflow-designer/select-rule-set-dialog-box-legacy.md)에서 **편집**을 선택합니다.  
  
         \-또는\-  
  
    -   규칙 집합의 이름을 입력합니다.**RuleSetReference** 속성을 확장하고 **RuleSet Definition** 속성에서 줄임표 **\[…\]**를 선택합니다.  
  
         [규칙 집합 편집기 대화 상자\(레거시\)](../workflow-designer/rule-set-editor-dialog-box-legacy.md)가 열립니다.  
  
4.  [규칙 집합 편집기 대화 상자\(레거시\)](../workflow-designer/rule-set-editor-dialog-box-legacy.md)에서 **규칙 추가**를 클릭하여 규칙 집합에 새 규칙을 추가합니다.  
  
5.  **이름**, **우선 순위** 및 **재계산** 속성을 입력하거나 기본값을 유지합니다.  
  
6.  **조건**에 텍스트를 입력합니다.  
  
7.  **ThenActions** 및 **Else 작업**에 텍스트를 입력합니다.  
  
8.  다른 규칙을 추가하려면 **규칙 추가**를 다시 클릭합니다.  
  
9. 마쳤으면 **확인**을 클릭합니다.  
  
## 참고 항목  
 [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)   
 [규칙 집합 선택 대화 상자\(레거시\)](../workflow-designer/select-rule-set-dialog-box-legacy.md)   
 [규칙 집합 편집기 대화 상자\(레거시\)](../workflow-designer/rule-set-editor-dialog-box-legacy.md)   
 [PolicyActivity 활동 사용](http://go.microsoft.com/fwlink?LinkID=65004)   
 [레거시 워크플로 활동](../workflow-designer/legacy-workflow-activities.md)