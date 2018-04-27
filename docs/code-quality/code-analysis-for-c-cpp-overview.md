---
title: C/C++용 코드 분석 개요
ms.date: 04/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- annotations, code analysis
- build integration, code analysis
- C/C++ code analysis
- IDE, code analysis
- pragma directive, code analysis
- code analysis, C/C++
- code analysis tool
- command line, code analysis
- C++, code analysis
- check-in policies, code analysis
- '#pragma directives, code analysis'
- C, code analysis
ms.assetid: 81f0c9e8-f471-4de5-aac4-99db336a8809
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- cplusplus
ms.openlocfilehash: ea576ba794350e6cee6b20f8ef9adb62f82a9c51
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="code-analysis-for-cc-overview"></a>C/c + + 개요에 대 한 코드 분석

C/c + + 코드 분석 도구는 C/c + + 소스 코드에서 발생할 수 있는 오류에 대 한 정보를 제공합니다. 이 도구를 통해 보고되는 일반적인 코딩 오류에는 버퍼 오버런, 초기화되지 않은 메모리, null 포인터 역참조, 메모리 및 리소스 누수 등이 포함됩니다. 도구에 대 한 검사를 실행할 수도 있습니다는 [c + + 코어 지침](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)합니다.

## <a name="ide-integrated-development-environment-integration"></a>IDE (통합된 개발 환경) 통합

코드 분석 도구는 Visual Studio IDE 내에서 완벽 하 게 통합 되어 있습니다.

소스 코드에 대 한 생성 된 경고는 빌드 프로세스 중 오류 목록에 표시 됩니다. 경고를 발생 시킨 소스 코드를 탐색할 수 및 해당 원인 및 문제 해결에 대 한 추가 정보를 볼 수 있습니다.

## <a name="command-line-support"></a>명령줄 지원

또한 다음 예에서 같이 명령줄에서 분석 도구를 사용할 수 있습니다.

```cmd
C:\>cl /analyze Sample.cpp
```

**Visual Studio 2017 버전 15.7 이상** CMake를 비롯 한 모든 빌드 시스템에서 명령줄 도구를 실행할 수 있습니다.

## <a name="pragma-support"></a>#pragma 지원

사용할 수는 `#pragma` 지시문으로 경고를 오류로 처리; 사용 하도록 설정 또는 경고를 해제 하 고 개별 코드 줄에 대 한 경고를 표시 합니다. 자세한 내용은 참조 [하는 방법: C/c + + 프로젝트에 대 한 코드 분석 속성 설정](how-to-set-code-analysis-properties-for-c-cpp-projects.md)합니다.

## <a name="annotation-support"></a>주석 지원

주석을 코드 분석의 정확도 향상 합니다. 주석이 함수 매개 변수에서 전처리 및 후 조건에 대 한 추가 정보를 제공 및 반환 형식입니다. 자세한 내용은 참조 [하는 방법: using __analysis_assume 사용 하 여 추가 코드 정보 지정](../code-quality/how-to-specify-additional-code-information-by-using-analysis-assume.md)

## <a name="run-analysis-tool-as-part-of-check-in-policy"></a>체크 인 정책의 일부로 분석 도구를 실행 합니다.

모든 소스 코드 체크 인 반드시 특정 정책 해야 할 수 있습니다. 특히, 가장 최근의 로컬 빌드 중 한 단계로 분석을 실행 하 고 있는지 확인 하려고 합니다. 코드 분석 체크 인 정책을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 참조 [만들기 및 사용 하 여 코드 분석 체크 인 정책](../code-quality/creating-and-using-code-analysis-check-in-policies.md)

## <a name="team-build-integration"></a>팀 빌드 통합

단계로 코드 분석 도구를 실행 하기 위해 빌드 시스템의 통합된 기능을 사용할 수 있습니다는 [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] 빌드 프로세스입니다. 자세한 내용은 [빌드 및 릴리스](/vsts/build-release/index)를 참조하세요.

## <a name="see-also"></a>참고자료

- [C/c + +에 대 한 빠른 시작: 코드 분석](quick-start-code-analysis-for-c-cpp.md)
- [연습: 오류에 대 한 C/c + + 코드 분석](walkthrough-analyzing-c-cpp-code-for-defects.md)
- [C/C++용 코드 분석 경고](code-analysis-for-c-cpp-warnings.md)
- [C++ Core Guidelines 검사기 사용](using-the-cpp-core-guidelines-checkers.md)
- [C + + 핵심 지침 검사기 참조](code-analysis-for-cpp-corecheck.md)
- [규칙 집합을 사용하여 실행할 C++ 규칙 지정](using-rule-sets-to-specify-the-cpp-rules-to-run.md)
- [코드 분석 도구를 사용 하 여 드라이버 품질 분석](/windows-hardware/drivers/develop/analyzing-driver-quality-by-using-code-analysis-tools)
- [드라이버 경고에 대 한 코드 분석](/windows-hardware/drivers/devtest/prefast-for-drivers-warnings)
