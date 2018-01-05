---
title: "방법: 솔루션의 여러 프로젝트에 대 한 관리 코드 규칙 집합 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.propertypages.solution
ms.assetid: 92dc3250-a010-4396-b515-f03a0b30cd2a
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 346ddadef815f4926b0a87a924a502ab2184de3e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution"></a>방법: 솔루션의 여러 프로젝트에 대한 관리 코드 규칙 집합 지정
기본적으로 솔루션의 모든 관리 되는 프로젝트에는 Microsoft 최소 권장 규칙 코드 분석 할당 된 *규칙 집합*합니다. 솔루션에 대 한 속성 대화 상자에서 솔루션의 프로젝트에 할당 된 규칙 집합을 변경할 수 있습니다.  
  
> [!NOTE]
>  기본적으로 코드 분석 프로젝트를 빌드 단계 실행 되지 않습니다. 코드 분석을 빌드 단계를 사용 하려면 참조 [하는 방법: 관리 코드 프로젝트에 대 한 코드 분석 구성](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)합니다.  
  
### <a name="to-specify-a-rule-set-for-multiple-projects-in-a-managed-code--solution"></a>관리 되는 코드 솔루션의 여러 프로젝트에 대 한 규칙 집합을 지정 하려면  
  
1.  [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)]합니다. [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)] 또는 [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]에서 솔루션을 엽니다.  
  
2.  에 **분석** 메뉴를 클릭 하 여 **솔루션에 대 한 코드 분석 구성**합니다.  
  
3.  필요한 경우 확장 **공용 속성**, 클릭 하 고 **코드 분석 설정**합니다.  
  
4.  하나 이상의 프로젝트에 대 한 규칙 집합을 지정할 수 있습니다.  
  
    -   개별 프로젝트에 대 한 규칙 집합을 지정 하려면 프로젝트 이름을 클릭 합니다.  
  
    -   여러 프로젝트에 대 한 규칙 집합을 지정 하려면 CTRL 키를 누른 채 하 고 프로젝트 이름을 클릭 합니다.  
  
    -   모든 프로젝트는 솔루션을 지정 하려면 SHIFT 키를 누른 채 마우스 프로젝트 목록에서 클릭 합니다.  
  
5.  클릭는 **규칙 집합** 클릭 적용 되도록 규칙의 이름을 설정 및 프로젝트의 필드입니다.