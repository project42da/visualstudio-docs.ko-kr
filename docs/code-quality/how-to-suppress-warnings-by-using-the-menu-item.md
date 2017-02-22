---
title: "방법: 메뉴 항목을 사용하여 경고 표시 안 함 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "경고, 표시 안 함"
  - "코드 분석, 경고 표시 안 함"
ms.assetid: 36bd1850-dcde-4ed0-9bc3-0b83df434362
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: 메뉴 항목을 사용하여 경고 표시 안 함
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

> [!NOTE]
>  C\/C\+\+ 및 웹 사이트 프로젝트에는 ISS\(In Source Suppression\)가 지원되지 않습니다.  
  
 오류 목록 창을 사용하여 관리 코드 분석 창을 표시하지 않을 수 있습니다.  경고를 억제 하는 사용 하지 않는 것 같습니다.  경고를 표시하지 않으면 특정 위반 인스턴스에만 이 설정이 적용됩니다.  다른 위반 인스턴스에 동일한 경고가 있으면 오류 목록 창에 보고됩니다.  
  
 코드 분석을 실행한 후 코드 분석을 창에 표시된 하나 이상의 코드 분석 경고가 응용 프로그램에 해당되지 않는 것인지 확인할 수 있습니다.  예를 들어 현재 코드가 올바른지 확인할 수 있습니다.  또는 위반의 우선 순위가 낮아 현재 개발 주기에서 수정되지 않은 경우에는 코드가 올바르지 않을 수도 있습니다.  어떤 이유로든 코드를 검토했으며 해당 경고를 표시하지 않기로 결정했음을 팀 구성원에게 알리기 위해 경고가 상황에 적합하지 않을 수 있도록 사실을 밝히는 것이 좋습니다.  ISS\(In Source Suppression\)를 사용하면 개발자의 경고가 생성된 위치 근처에 경고를 표시하지 않도록 하는 데코레이션을 배치할 수 있으므로 유용합니다.  
  
 비표시 오류\(Suppression\)를 소스 코드에 표시할지, 아니면 전역 비표시 오류\(Suppression\) 파일에 표시할지를 선택할 수 있습니다.  일부 비표시 오류\(Suppression\)는 전역 비표시 오류\(Suppression\) 파일에 배치해야 합니다.  이 경우 **소스** 옵션은 사용할 수 없습니다.  
  
### 메뉴 항목을 사용하여 경고를 표시하지 않도록 설정하려면  
  
1.  **디버그** 메뉴에서 **창**을 선택한 다음 **Code Analysis**를 선택합니다.  
  
2.  **Code Analysis**창에서 코드 분석 경고를 선택 합니다.  
  
3.  작업을 선택한 다음 선택  **메시지 표시 안 함**를 다음 중 하나를 선택 하 고  **소스에** 또는 **프로젝트 비 표시 오류 파일**을 선택합니다.  
  
     해당 경고가 표시되지 않으며 Code Analysis 창에는 해당 경고가 취소선이 그어진 상태로 나타납니다.  
  
> [!NOTE]
>  대상이 없는 비표시 오류\(Suppression\)는 전역 비표시 오류 파일에 나타납니다.