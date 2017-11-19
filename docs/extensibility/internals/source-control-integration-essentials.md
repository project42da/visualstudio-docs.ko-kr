---
title: "소스 제어 통합 Essentials | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Source Control Integration, essentials
- Source Control Integration,overview
- essentials, Source Control Integration
ms.assetid: 442057cb-fd54-4283-96f8-2f6dc8bf2de7
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 09e96719bd7d9a2091bf31dc343036f0312c02fc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="source-control-integration-essentials"></a>소스 제어 통합 Essentials
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에서는 두 가지 소스 제어 통합: (이전의 MSSCCI API), 소스 제어 플러그 인 API 및 VSPackage 기반 소스 제어 통합 솔루션을 사용 하 여 만들어집니다 및 기본 기능을 제공 하는 소스 제어 플러그 인입니다 보다 강력한 기능을 제공 합니다.  
  
## <a name="source-control-plug-in"></a>소스 제어 플러그 인  
 소스 제어 플러그 인 소스 제어 플러그 인 API를 구현 하는 DLL로 기록 됩니다. 등록 및 소스 제어 통합 기능은 API를 통해 제공 됩니다. 이 방법은 소스 제어 VSPackage 보다 구현 하기가 사용 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 대부분 소스 제어 작업에 대 한 사용자 인터페이스 (UI).  
  
 소스 제어 플러그 인 API를 사용 하 여 플러그 인 소스 제어를 구현 하려면 다음이 단계를 따르십시오.  
  
1.  에 지정 된 함수를 구현 하는 DLL을 만드는 [소스 제어 플러그 인](../../extensibility/source-control-plug-ins.md)합니다.  
  
2.  에 설명 된 대로 적절 한 레지스트리 항목을 만들어서 DLL을 등록 [하는 방법: 소스 제어 플러그 인 설치](../../extensibility/internals/how-to-install-a-source-control-plug-in.md)합니다.  
  
3.  도우미 UI를 만들고 표시 하는 소스 제어 어댑터 패키지에서 메시지를 표시 하는 경우 (의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 제어 플러그 인을 통해 소스 제어 기능을 처리 하는 구성 요소).  
  
 자세한 내용은 참조 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md)합니다.  
  
## <a name="source-control-vspackage"></a>소스 제어 VSPackage  
 소스 제어 VSPackage 구현에 대 한 사용자 지정 된 대체를 개발할 수는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 UI 컨트롤입니다. 이 방법은 소스 제어 통합을 완전히 제어를 제공 하지만 하 UI 요소를 제공 하 고 그렇지 않으면 플러그 인 접근 방식에서 제공 되는 소스 제어 인터페이스를 구현 해야 합니다.  
  
 소스 제어 VSPackage를 구현 하려면 다음을 수행 해야 합니다.  
  
1.  만들고에 설명 된 대로 사용자 고유의 소스 제어 VSPackage 등록 [등록 및 선택](../../extensibility/internals/registration-and-selection-source-control-vspackage.md)합니다.  
  
2.  기본 소스 제어를 UI를 사용자 지정 UI를 바꿉니다. 참조 [사용자 지정 사용자 인터페이스](../../extensibility/internals/custom-user-interface-source-control-vspackage.md)합니다.  
  
3.  사용 되 고 처리 문자 모양을 지정 **솔루션 탐색기** 문자 모양 이벤트입니다. 참조 [문자 모양 컨트롤](../../extensibility/internals/glyph-control-source-control-vspackage.md)합니다.  
  
4.  쿼리 편집 및 쿼리 저장 이벤트를 처리 하 여에 나와 있는 것 처럼 [쿼리 편집 쿼리 저장](../../extensibility/internals/query-edit-query-save-source-control-vspackage.md)합니다.  
  
 자세한 내용은 참조 [소스 제어 VSPackage 만들기](../../extensibility/internals/creating-a-source-control-vspackage.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개요](../../extensibility/internals/source-control-integration-overview.md)   
 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md)   
 [소스 제어 VSPackage 만들기](../../extensibility/internals/creating-a-source-control-vspackage.md)