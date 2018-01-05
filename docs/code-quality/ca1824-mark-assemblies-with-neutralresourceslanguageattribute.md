---
title: "CA1824: NeutralResourcesLanguageAttribute로 어셈블리 표시 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1824
- MarkAssembliesWithNeutralResourcesLanguage
helpviewer_keywords:
- MarkAssembliesWithNeutralResourcesLanguage
- CA1824
ms.assetid: 10e97f8a-aa6e-47aa-b253-1e5d3a295d82
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6c9d4da3becaa6831f30a5cc6c72d1f0b3b70eea
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1824-mark-assemblies-with-neutralresourceslanguageattribute"></a>CA1824: NeutralResourcesLanguageAttribute로 어셈블리 표시
|||  
|-|-|  
|TypeName|MarkAssembliesWithNeutralResourcesLanguage|  
|CheckId|CA1824|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 포함 된 어셈블리는 **ResX**-리소스를 기반으로 하지만 없는 <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> 적용 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 **NeutralResourcesLanguage** 특성은 **ResourceManager** 어셈블리에 대 한 중립 문화권의 리소스를 표시 하는 데 사용 된 언어의 합니다. 중립 리소스 언어와 같은 문화권의 리소스를 조회 하는 경우는 **ResourceManager** 주 어셈블리에 있는 리소스를 자동으로 사용 합니다. 현재 스레드에 대 한 현재 사용자 인터페이스 문화권을 포함 하는 위성 어셈블리를 검색 하지는 않습니다. 이렇게 하면 로드한 첫 리소스에 대한 찾기 성능을 향상시킬 수 있으며 작업이 간단해집니다.  
  
## <a name="fixing-violations"></a>위반 문제 해결  
 이 규칙 위반 문제를 해결 하는 어셈블리에 특성을 추가 하 고 중립 문화권의 리소스의 언어를 지정 합니다.  
  
## <a name="specifying-the-language"></a>언어 지정  
  
#### <a name="to-specify-the-language-of-the-resource-of-the-neutral-culture"></a>중립 문화권의 리소스의 언어를 지정 하려면  
  
1.  **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다.  
  
2.  왼쪽된 탐색 모음에서 선택 **응용 프로그램**, 클릭 하 고 **어셈블리 정보**합니다.  
  
3.  에 **어셈블리 정보** 대화 상자에서 언어를 선택 합니다는 **중립 언어** 드롭 다운 목록입니다.  
  
4.  **확인**을 클릭합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를에서 표시 하지 않을 경우합니다 그러나 시작 성능이 저하 될 수 있습니다.