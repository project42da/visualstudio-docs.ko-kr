---
title: "C/C++용 코드 분석 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "#pragma 지시문, 코드 분석"
  - "주석, 코드 분석"
  - "빌드 통합, 코드 분석"
  - "C, 코드 분석"
  - "C/C++ 코드 분석"
  - "C++, 코드 분석"
  - "체크 인 정책, 코드 분석"
  - "코드 분석 도구"
  - "코드 분석, C/C++"
  - "명령줄, 코드 분석"
  - "IDE, 코드 분석"
  - "pragma 지시문, 코드 분석"
ms.assetid: 81f0c9e8-f471-4de5-aac4-99db336a8809
caps.latest.revision: 25
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C/C++용 코드 분석 개요
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

C\/C\+\+ 코드 분석 도구는 C\/C\+\+ 소스 코드에서 발생할 수 있는 오류에 대한 정보를 개발자에게 제공합니다.  이 도구를 통해 보고되는 일반적인 코딩 오류에는 버퍼 오버런, 초기화되지 않은 메모리, null 포인터 역참조, 메모리 및 리소스 누수 등이 포함됩니다.  
  
## IDE\(통합 개발 환경\) 통합  
 개발자가 자연스럽게 분석 도구를 사용할 수 있도록 분석 도구가 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE에 완벽하게 통합되었습니다.  빌드 프로세스에서 소스 코드에 대해 생성된 경고가 오류 목록에 나타납니다.  경고를 발생시킨 소스 코드로 이동하고, 해당 문제의 원인과 가능한 해결 방법에 대한 추가 정보를 볼 수 있습니다.  
  
## \#pragma 지원  
 개발자는 `#pragma` 지시문을 사용하여 경고를 오류로 처리하고, 경고를 사용하거나 사용하지 않도록 설정하고, 개별 코드 줄에 대해 경고를 표시하지 않을 수 있습니다.  자세한 내용은 [How to: Enable and Disable Code Analysis for Specific C\/C\+\+ Warnings](http://msdn.microsoft.com/ko-kr/910b8518-71f1-4b2e-b012-70647795642a)을 참조하십시오.  
  
## 주석 지원  
 주석을 사용하면 코드 분석의 정확성이 높아집니다.  주석은 함수 매개 변수와 반환 형식에 대해 pre 및 post 조건에 대한 정보를 제공합니다.  자세한 내용은 [How to: Using \_\_analysis\_assume 사용하여 추가 코드 정보 지정](../Topic/How%20to:%20Specify%20Additional%20Code%20Information%20by%20Using%20__analysis_assume.md)을 참조하십시오.  
  
## 체크 인 정책의 일부로 분석 도구 실행  
 모든 소스 코드 체크 인이 반드시 특정 정책을 따르도록 할 수 있습니다.  특히 가장 최근 논리 빌드의 한 단계로 분석을 실행했는지 확인할 수 있습니다.  코드 분석 체크 인 정책을 사용하도록 설정하는 방법에 대한 자세한 내용은 [코드 분석 체크 인 정책 만들기 및 사용](../code-quality/creating-and-using-code-analysis-check-in-policies.md)을 참조하십시오.  
  
## 팀 빌드 통합  
 빌드 시스템의 통합된 기능을 사용하여 [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] 빌드 프로세스의 한 단계로 코드 분석 도구를 실행할 수 있습니다.  자세한 내용은 [응용 프로그램 빌드](../Topic/Build%20the%20application.md)을 참조하십시오.  
  
## 명령줄 지원  
 개발 환경 내에 완벽하게 통합된 분석 도구 외에 개발자는 다음 예제처럼 명령줄에서도 분석 도구를 사용할 수 있습니다.  
  
 `C:\>cl /analyze Sample.cpp`