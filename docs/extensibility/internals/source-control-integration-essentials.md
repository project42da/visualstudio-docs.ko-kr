---
title: "소스 제어 통합 Essentials | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 통합, essentials"
  - "소스 제어 통합, 개요"
  - "essentials, 소스 제어 통합"
ms.assetid: 442057cb-fd54-4283-96f8-2f6dc8bf2de7
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# 소스 제어 통합 Essentials
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]두 가지 유형의 소스 제어 통합을 지원 합니다: 기본 기능을 제공 하 고 소스 제어 플러그 인 \(이전의 MSSCCI API로\) API를 사용 하 여 작성 되는 소스 제어 플러그 인와 더욱 강력한 기능을 제공 하는 VSPackage 기반 소스 제어 통합 솔루션입니다.  
  
## 소스 제어 플러그 인  
 소스 제어 플러그 인은 소스 제어 플러그 인 API를 구현 하는 DLL로 작성 됩니다.  등록 및 소스 제어 통합 기능에는 API는 통해 제공 됩니다.  소스 컨트롤 Vspackage를 보다 쉽게이 방법 이며이 사용 하 여 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 대부분의 소스 제어 작업에 대 한 사용자 인터페이스 \(UI\)입니다.  
  
 소스 제어 플러그 인 API를 사용 하 여 플러그 인을 구현 하려면 다음과 같이 하십시오.  
  
1.  지정 된 함수를 구현 하는 DLL을 만드는 [소스 제어 플러그 인](../../extensibility/source-control-plug-ins.md).  
  
2.  에 설명 된 대로 적절 한 레지스트리 항목을 변경 하 여 DLL을 등록 [방법: 소스 제어 플러그 인 설치](../../extensibility/internals/how-to-install-a-source-control-plug-in.md).  
  
3.  도우미 UI를 만들고 원본 컨트롤 어댑터 패키지에서 메시지가 표시 되 면 표시 \(는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 제어 플러그 인을 통해 소스 제어 기능을 처리 하는 구성 요소\)입니다.  
  
 자세한 내용은 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md)를 참조하십시오.  
  
## 소스 제어 VSPackage  
 소스 제어 구현 VSPackage 개발에 대 한 사용자 지정된 대체 수 있습니다의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 원본 컨트롤 UI입니다.  이 방법은 소스 제어 통합을 통해 완벽 한 제어를 제공 하지만 UI 요소를 제공 하 고 플러그 인 접근 방식에서 제공 되는 소스 컨트롤 인터페이스를 구현 해야 합니다.  
  
 소스 제어 Vspackage를 구현 하려면 다음을 수행 해야 합니다.  
  
1.  만들고 Vspackage를 소스 제어에 설명 된 대로 등록 [등록 및 선택](../../extensibility/internals/registration-and-selection-source-control-vspackage.md).  
  
2.  기본 소스 제어 UI와 사용자 지정 UI를 대체 합니다.  자세한 내용은 [사용자 지정 사용자 인터페이스](../../extensibility/internals/custom-user-interface-source-control-vspackage.md)를 참조하십시오.  
  
3.  문자 모양을 사용할 수와 처리 수 지정  **솔루션 탐색기** 문자 이벤트입니다.  자세한 내용은 [문자 모양 제어](../../extensibility/internals/glyph-control-source-control-vspackage.md)를 참조하십시오.  
  
4.  과 같이 이벤트 쿼리를 편집 하 고 쿼리를 저장, 처리 [쿼리 저장 쿼리 편집](../../extensibility/internals/query-edit-query-save-source-control-vspackage.md).  
  
 자세한 내용은 [소스 제어 VSPackage 만들기](../../extensibility/internals/creating-a-source-control-vspackage.md)를 참조하십시오.  
  
## 참고 항목  
 [개요](../../extensibility/internals/source-control-integration-overview.md)   
 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md)   
 [소스 제어 VSPackage 만들기](../../extensibility/internals/creating-a-source-control-vspackage.md)