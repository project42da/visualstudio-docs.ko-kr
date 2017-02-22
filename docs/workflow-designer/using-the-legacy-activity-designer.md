---
title: "레거시 활동 디자이너 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "활동, 자식 추가"
  - "활동, 구성"
  - "활동, 사용자 지정 만들기"
  - "활동 디자이너"
  - "자식 활동, 추가"
  - "사용자 지정 활동"
ms.assetid: 2fea8a05-6e58-423d-94bf-a822b15ffb80
caps.latest.revision: 5
caps.handback.revision: 5
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# 레거시 활동 디자이너 사용
이 항목에서는 레거시 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]에서 활동 디자이너를 사용하는 방법에 대해 설명합니다.레거시 디자이너는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 하는 경우에 사용합니다.  
  
 활동 디자이너를 사용하면 사용자 지정 활동을 직접 만들 수 있습니다.  
  
## 사용자 지정 활동 만들기  
 활동 디자이너를 사용하여 사용자 지정 활동을 만들려면 다음 단계를 따르십시오.  
  
1.  **프로젝트** 메뉴에서 **활동 추가**를 클릭합니다.  
  
2.  **활동** 또는 **활동\(코드 분리\)** 템플릿을 선택합니다.  
  
    1.  활동 정의와 사용자 코드가 동일한 코드 파일에 있는 활동을 만들려면 **활동** 템플릿을 사용합니다.  
  
    2.  활동 정의가 워크플로 마크업으로 표현되고 별도의 코드 파일에 사용자 코드가 있는 활동을 만들려면 **활동\(코드 분리\)** 템플릿을 사용합니다.  
  
3.  활동 이름을 입력하거나 기본 이름을 유지하고 **추가**를 클릭합니다.  
  
 **Workflow Activity Library** 형식의 새 프로젝트를 만들어 사용자 지정 활동 집합을 만들 수도 있습니다.이 프로젝트 형식에 대한 자세한 내용은 [방법: 워크플로 활동 라이브러리 만들기\(레거시\)](../Topic/How%20to:%20Create%20a%20Workflow%20Activity%20Library%20\(Legacy\).md)를 참조하십시오.  
  
## 활동 구성  
 활동 디자이너가 활성 상태일 때 속성 브라우저를 사용하여 다음 표에 나열된 속성을 구성할 수 있습니다.  
  
|속성|설명|  
|--------|--------|  
|**Name**|활동 이름입니다.|  
|**Base Class**|활동이 파생되는 기본 클래스입니다.기본 클래스의 기본값은 [SequenceActivity](http://go.microsoft.com/fwlink?LinkID=65020)\(영문 페이지일 수 있음\)입니다.[.NET 유형 선택 대화 상자\(레거시\)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md)에서 다른 기본 클래스를 선택하려면 **속성** 창에서 **Base 클래스** 줄임표 **\[…\]**를 클릭합니다.|  
|**Description**|활동의 사용자 정의 설명입니다.|  
|**Enabled**|활동 실행 및 유효성 검사가 가능하도록 기본적으로 **True**로 설정합니다.활동 실행 및 유효성 검사를 하지 않으려면 **False**로 설정합니다.활동 실행 및 유효성 검사에 대한 자세한 내용은 [워크플로 활동 개발](http://go.microsoft.com/fwlink?LinkID=65024)\(영문 페이지일 수 있음\)을 참조하십시오.|  
  
## 자식 활동 추가  
 도구 상자에서 디자인 중인 활동으로 자식 활동을 끌어 놓을 수 있습니다.그런 다음 속성 브라우저를 사용하여 각 자식 활동을 구성할 수 있습니다.  
  
## 참고 항목  
 [워크플로 활동 개발](http://go.microsoft.com/fwlink?LinkID=65024)   
 [사용자 지정 활동 만들기](http://go.microsoft.com/fwlink?LinkID=65021)   
 [레거시 워크플로 활동](../workflow-designer/legacy-workflow-activities.md)   
 [사용자 지정 활동 샘플](http://go.microsoft.com/fwlink?LinkID=65022)   
 [방법: 워크플로 활동 라이브러리 만들기\(레거시\)](../Topic/How%20to:%20Create%20a%20Workflow%20Activity%20Library%20\(Legacy\).md)   
 [레거시 Workflow Designer 사용](../workflow-designer/using-the-legacy-workflow-designer.md)