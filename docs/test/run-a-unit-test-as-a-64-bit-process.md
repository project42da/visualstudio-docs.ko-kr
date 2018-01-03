---
title: "단위 테스트를 64비트 프로세스로 실행 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unit tests, creating
- unit tests, running
ms.assetid: d23a9ee7-58e3-4e8b-a38c-b2207ea73fea
caps.latest.revision: "25"
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: 39addca0d673ae5a9423d4195ffc2bfe3358de4e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="run-a-unit-test-as-a-64-bit-process"></a>단위 테스트를 64비트 프로세스로 실행
64비트 컴퓨터를 사용하는 경우에는 단위 테스트를 실행하고 코드 검사 정보를 64비트 프로세스로 캡처할 수 있습니다.  
  
## <a name="running-a-unit-test-as-a-64-bit-process"></a>단위 테스트를 64비트 프로세스로 실행  
  
#### <a name="to-run-a-unit-test-as-a-64-bit-process"></a>단위 테스트를 64비트 프로세스로 실행하려면  
  
1.  코드 또는 테스트를 32비트/x86으로 컴파일했지만 64비트 프로세스로 실행하려면 **모든 CPU** 또는 원한다면 **64비트**로 다시 컴파일합니다.  
  
    > [!TIP]
    >  유연성을 극대화하려면 **Any CPU** 구성으로 테스트 프로젝트를 컴파일해야 합니다. 그러면 32 비트 및 64비트 에이전트에서 모두 실행할 수 있습니다. **64비트** 구성으로 테스트 프로젝트를 컴파일하는 것은 아무 이점이 없습니다.  
  
2.  Visual Studio 메뉴에서 **테스트**, **설정**, **프로세서 아키텍처**를 차례로 선택합니다. **x64**를 선택해서 테스트를 64비트 프로세스로 실행합니다.  
  
     \- 또는 -  
  
     .runsettings 파일에서 `<TargetPlatform>x64</TargetPlatform>`을 지정합니다. 이 메서드의 장점은 서로 다른 파일에서 설정 그룹을 지정하고 각 설정 간에 빠르게 전환할 수 있다는 점입니다. 또한 솔루션 간에 설정을 복사할 수도 있습니다. 자세한 내용은 [.runsettings 파일을 사용하여 단위 테스트 구성](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [테스트 탐색기를 사용하여 단위 테스트 실행](../test/run-unit-tests-with-test-explorer.md)   
 [코드 단위 테스트](../test/unit-test-your-code.md)   
 [Visual Studio 테스트에 대한 테스트 설정 지정](/devops-test-docs/test/specifying-test-settings-for-visual-studio-tests)
