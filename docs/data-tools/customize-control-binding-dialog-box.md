---
title: "컨트롤 바인딩 사용자 지정 대화 상자 | Microsoft Docs"
ms.custom: ""
ms.date: "09/21/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.datasource.datauicustomization"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "컨트롤 바인딩 사용자 지정 대화 상자"
ms.assetid: abcc0be3-a18e-4f47-b354-d6b0c618e087
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 컨트롤 바인딩 사용자 지정 대화 상자
**컨트롤 바인딩 사용자 지정** 대화 상자를 사용하여 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)의 항목에 사용할 수 있는 컨트롤을 지정합니다.  
  
 **데이터 소스** 창의 각 항목에는 해당 항목에 바인딩할 수 있는 컨트롤의 목록이 연결되어 있습니다.  각 항목에 대해 사용할 수 있는 컨트롤은 해당 항목의 데이터 형식에 의해 결정됩니다.  각 데이터 형식에는 기본 컨트롤을 포함하여 이 대화 상자에 정의된 올바른 연결 컨트롤 목록이 있습니다.  
  
 항목을 디자인 화면으로 끌어 데이터 바인딩된 컨트롤을 만들기 전에 만들 컨트롤을 선택할 수 있습니다.  컨트롤을 선택하지 않고 **데이터 소스** 창에서 디자인 화면으로 항목을 끌면 선택한 항목의 데이터 형식에 대한 기본 컨트롤이 디자인 화면에 추가됩니다.  
  
 이 대화 상자를 사용하여 **데이터 소스** 창의 항목에 대한 컨트롤 목록을 사용자 지정하는 방법에 대한 자세한 내용은 [데이터 소스 창에 사용자 지정 컨트롤 추가](../data-tools/add-custom-controls-to-the-data-sources-window.md)를 참조하십시오.  
  
## UI 요소 목록  
 **데이터 형식**  
 컨트롤에 연결할 형식 목록을 표시합니다.  
  
-   테이블, 엔터티 및 개체는 **\[목록\]** 형식으로 표시됩니다.  
  
-   엔터티와 개체의 열 또는 공용 속성은 내부 데이터 저장소에 있는 열 또는 속성의 실제 데이터 형식으로 표시됩니다.  
  
-   사용자 정의 모양이 포함된 개체는 **\[기타\]**로 표시됩니다.  예를 들어, 응용 프로그램에 개체의 속성 중 두 가지 이상을 사용하여 데이터를 표시하는 사용자 지정 컨트롤이 있으면 컨트롤의 데이터 형식을 **\[기타\]**로 선택합니다.  
  
 **연결된 컨트롤**  
 특정 데이터 형식에 연결할 수 있는 컨트롤의 목록을 표시합니다.  특정 컨트롤을 **데이터 형식** 목록에서 선택한 형식에 연결하려면 해당 확인란을 선택합니다.  연결을 취소하려면 확인란의 선택을 취소합니다.  선택한 컨트롤은 연결된 데이터 형식의 항목에 대한 **데이터 소스** 창의 바로 가기 메뉴에 나타납니다.  
  
 여러 개의 데이터 바인딩 특성 중 하나가 있는 컨트롤을 **도구 상자**에 추가하여 컨트롤을 목록에 추가할 수 있습니다.  자세한 내용은 [데이터 소스 창에 사용자 지정 컨트롤 추가](../data-tools/add-custom-controls-to-the-data-sources-window.md)를 참조하십시오.  
  
 **기본값 설정**  
 선택한 데이터 형식의 항목에 대해 선택된 컨트롤 형식이 기본값이 되도록 할당합니다.  기본 컨트롤은 항목에 대한 **데이터 소스** 창의 바로 가기 메뉴에 첫 번째 선택 항목으로 나타납니다.  데이터 형식에 대해서는 하나의 컨트롤 형식만 기본값으로 할당할 수 있습니다.  
  
 **기본값 지우기**  
 선택한 데이터 형식의 기본값으로 지정된 컨트롤 할당을 취소합니다.  선택한 데이터 형식에 대한 기본값이 없으면 연결된 형식의 항목에 대한 **데이터 소스** 창의 바로 가기 메뉴에 **\[없음\]**이 첫 번째 선택 항목으로 나타납니다.  
  
## 참고 항목  
 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)   
 [데이터 소스 개요](../data-tools/add-new-data-sources.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [데이터 소스 창에 사용자 지정 컨트롤 추가](../data-tools/add-custom-controls-to-the-data-sources-window.md)   
 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)