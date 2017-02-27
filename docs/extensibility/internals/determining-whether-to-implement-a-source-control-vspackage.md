---
title: "소스 제어 VSPackage를 구현할지 여부를 결정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 패키지에 대 한 소스 제어 패키지"
ms.assetid: 60b3326e-e7e2-4729-95fc-b682e7ad5c99
caps.latest.revision: 24
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 24
---
# 소스 제어 VSPackage를 구현할지 여부를 결정
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 섹션에서는 VSPackages 소스 제어와 소스 제어 플러그 인을 선택한 소스 제어에 적합 한 통합 경로 선택에 대 한 솔루션 제공 하 고 광범위 한 지침 확장에 대 한 자세히 다루고 있습니다.  
  
## 제한 된 리소스로 작은 소스 제어 솔루션  
 소스 제어 패키지를 작성 하는 오버 헤드를 burdened 수 없는 리소스가 제한 되어 있으면 플러그 인 소스 제어 플러그 인 API를 기반으로 만들 수 있습니다.  소스 제어 패키지 함께 작업할 수 있습니다와 소스 제어 플러그 인 및 주문형 패키지 간에 전환할 수 있습니다.  자세한 내용은 [등록 및 선택](../../extensibility/internals/registration-and-selection-source-control-vspackage.md)를 참조하십시오.  
  
## 많은 소스 제어 솔루션, 풍부한 기능으로 설정합니다.  
 소스 제어 플러그 인 API를 사용 하 여 제대로 캡처되지 않습니다 풍부한 소스 컨트롤 모델을 제공 하는 소스 제어 솔루션을 구현 하려는 경우와 통합 경로 소스 제어 패키지를 고려할 수 있습니다.  특히 \(는 소스 제어 플러그 인에 전달 하 고 제공 하는 기본 원본 컨트롤 UI\) 소스 컨트롤 어댑터 패키지를 대신 대체 합니다 경우에 소스 컨트롤 이벤트를 사용자 지정 방식으로 처리할 수 있도록 사용자로 지정 됩니다.  만족 스런 UI를 제어 하 고이 경험을 보존 하 시겠습니까 소스를 이미 있는 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 소스 제어 패키지 옵션을 사용 하는 이러한 작업 수 있습니다.  소스 제어 패키지 일반 이며 전적으로 사용 하기 위해 설계 되었습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
 소스 제어 논리와 UI 보다 다양 한 제어 및 유연성을 제공 하는 소스 제어 솔루션을 구현 하려는 경우 소스 제어 패키지 통합 경로 수도 있습니다.  다음과 같은 작업을 수행할 수 있습니다.  
  
1.  VSPackage 소스 제어 레지스터 \(참조 하십시오 [등록 및 선택](../../extensibility/internals/registration-and-selection-source-control-vspackage.md)\).  
  
2.  기본 소스 제어 UI와 사용자 지정 UI를 교체 \(참조 하십시오 [사용자 지정 사용자 인터페이스](../../extensibility/internals/custom-user-interface-source-control-vspackage.md)\).  
  
3.  지정 문자 모양을 사용할 수 있으며 솔루션 탐색기 문자 모양 이벤트를 처리 합니다 \(표시 [문자 모양 제어](../../extensibility/internals/glyph-control-source-control-vspackage.md)\).  
  
4.  쿼리를 편집 하 고 쿼리를 저장 하는 이벤트를 처리 \(참조 하십시오 [쿼리 저장 쿼리 편집](../../extensibility/internals/query-edit-query-save-source-control-vspackage.md)\).  
  
## 참고 항목  
 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md)