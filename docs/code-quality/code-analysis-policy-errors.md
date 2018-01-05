---
title: "코드 분석 정책 오류 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.policyfailures
helpviewer_keywords: policy errors, code analysis
ms.assetid: d1f221cd-68c0-4277-9397-b76ad0dbae77
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 268940f39d3d74e7dd701f9c458d7dd08ff6c1f7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="code-analysis-policy-errors"></a>코드 분석 정책 오류
체크 인 시에 코드 분석 정책이 충족 되지 않은 다음과 같은 오류가 발생 합니다.  
  
 **하나 이상의 프로젝트에 대 한 코드 분석 설정이 코드 분석 정책과 호환 되지 않습니다.**  
  
 코드 분석의 팀 프로젝트 소스 제어에 대한 체크 인 요구 사항이 하나 이상의 코드 프로젝트에서 충족되지 않았습니다. 이 오류는 다음과 같은 하나 이상의 조건에 의해 발생할 수 있습니다.  
  
1.  솔루션에 있는 모든 프로젝트에 대해 코드 분석이 빌드 시에 설정되지 않았습니다.  
  
2.  로컬 규칙 집합에 Visual Studio에서 프로젝트 덜 제한적인 **동작** 는 팀 프로젝트 규칙 집합 예를 들어로 설정 하는 규칙 보다 설정 **동작**=**오류**  서버에 해당 **동작** 로 설정 **경고** 또는 **None** 규칙 Visual Studio에서 실행 되 고 집합에).  
  
3.  Visual Studio에 지정된 규칙 집합은 팀 프로젝트에 대한 코드 분석 체크 인 정책에 지정된 규칙 집합에 지정된 모든 규칙이 포함되지 않습니다.  
  
 **코드 분석 정책 실패 했습니다. 프로젝트 {0}에는 오류 또는 빌드는 최신 버전입니다.**  
  
 빌드에 오류가 오류 수정 되었지만 수정 후 코드 분석을 수행 하지 못했습니다.  
  
 **체크 인에 실패 했습니다. 코드 분석 정책 체크 인하는 Visual Studio를 통해에서 열려 있는 솔루션 필요 합니다.**  
  
 코드 분석 정책 체크 인 모든 파일을 현재 열려 있는 솔루션에 되어야 함이 필요 합니다. 이 오류를 해결 하려면 체크 인 파일이 포함 된 솔루션을 엽니다.  
  
 **보류 중인 체크 인에 일부 파일이 현재 열려 있는 솔루션 내에서 됩니다.**  
  
 코드 분석 정책 체크 인 모든 파일을 현재 열려 있는 솔루션에 되어야 함이 필요 합니다. 이 오류는 열려 있는 솔루션이 있지만 일부 파일을 "보류 중인 체크 인" 보기에서 현재 열려 있는 솔루션의 일부가 아닌 경우에 발생 합니다. 이 오류를 해결 하려면 체크 인 파일이 포함 된 솔루션을 엽니다.  
  
 **' {'이 (0)의 버전이 올바르지 않습니다. 강력한-지정 된 정책에 이름이 '{1 \} '입니다.**  
  
 이 오류는.NET 프로젝트에 적용 됩니다. 코드 분석 정책에 필요한 규칙.dll 로컬 컴퓨터에 있지만 버전/공개 키와 일치 하지 않습니다. 이 오류를 해결 하려면 정책을 만든 사람이에.dll을 업데이트 해야 *C:\Program Files\Microsoft Visual Studio 8\Team Tools\Static Analysis Tools\FxCop\Rules\\*  자신의 컴퓨터에서 디렉터리입니다.  
  
 **' {'이 (0) 정책에 지정 된 어셈블리 존재 하지 않습니다.**  
  
 이 오류는.NET 프로젝트에 적용 됩니다. 코드 분석 정책에 필요한 규칙에는 클라이언트 컴퓨터에 설치 된 해당 dll이 없습니다. 이 오류를 해결 하려면 정책을 만든 사람이에서 dll을 업데이트 해야 *C:\Program Files\Microsoft Visual Studio 8\Team Tools\Static Analysis Tools\FxCop\Rules\\*  자신의 컴퓨터에서 디렉터리입니다.  
  
 **프로젝트 {0} 규칙 설정이 코드 분석 정책 따르지에서 않습니다.**  
  
 이 오류는.NET 프로젝트에 적용 됩니다. 관리 코드 규칙 설정은 정책에 필요한 만큼 엄격한입니다. 이 오류를 해결 하려면 클라이언트 설정이 동일 해야 하거나 서버에 정책 요구 사항이 보다 엄격 합니다.  
  
 **코드 분석 활성 구성에 사용 되지 않습니다. 구성 {0} 전환한 체크 인하기 전에 프로젝트 {1 \}를 작성 합니다.**  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 활성 구성에는 코드 분석을 사용 하지만 하나 이상의 코드 분석을 사용 하도록 설정 합니다.  
  
 **{0} 프로젝트 속성에서 관리 되는 이진에 대 한 코드 분석을 사용 하도록 설정 하 고 체크 인하기 전에 빌드 해야 합니다.**  
  
 이 오류에 적용 됩니다 [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] .NET 응용 프로그램입니다. 정책에 따라 관리 되는 코드 분석을 수행할 수 있지만 클라이언트에서 현재 프로젝트에서 사용할 수 없습니다.  
  
 **코드 분석 프로젝트 {0} 속성에서 사용 하도록 설정 하 고 체크 인하기 전에 빌드 해야 합니다.**  
  
 이 오류는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트와 웹 프로젝트입니다. 정책에 따라 관리 되는 코드 분석을 수행할 수 있지만 클라이언트에서 현재 프로젝트에서 사용할 수 없습니다.  
  
 **C/c + + 코드 분석 프로젝트 {0} 속성에서 사용 하도록 설정 하 고 체크 인하기 전에 빌드 해야 합니다.**  
  
 이 오류는 관리 되지 않는 프로젝트에 적용 됩니다. 코드 분석 정책 C/c + + 코드 분석 하는데 클라이언트에서 현재 프로젝트에서 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [코드 분석 응용 프로그램 오류](../code-quality/code-analysis-application-errors.md)