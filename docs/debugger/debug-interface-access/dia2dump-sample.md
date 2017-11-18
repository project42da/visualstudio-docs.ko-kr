---
title: "Dia2dump 샘플 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- sample applications [DIA SDK]
- Dia2dump sample [DIA SDK]
ms.assetid: 492c0893-7043-452f-a020-890a47230d20
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1a3166065680c193875c451626846a090e50cbc1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="dia2dump-sample"></a>Dia2dump 샘플
Dia2dump 샘플 Visual Studio와 함께 설치 되어 있고 Dia2dump.cpp 소스 파일을 포함 합니다. 명령줄에서 실행 하 고 전체 프로그램 데이터베이스 (.pdb) 파일의 내용을 표시 하는 컴파일된 실행 파일입니다.  
  
### <a name="to-install-the-sample"></a>이 샘플을 설치 하려면  
  
1.  시스템에 Visual Studio 설치 프로그램 시작 페이지에서 설명 하는 모든 설치 요구 사항을 충족 하는지 확인 합니다.  
  
2.  Visual Studio를 설치 하 고 포함 된 샘플에 대 한 모든 설정 및 설치 지침을 따릅니다.  
  
#### <a name="to-build-the-sample"></a>이 샘플을 빌드하려면  
  
1.  Visual Studio에서 Dia2dump.sln 파일을 엽니다. (필요한 경우 Visual Studio 먼저 할 Dia2dump 프로젝트 업그레이드 있습니다.)  
  
2.  프로젝트 속성 페이지에서에 **C/c + +** &#124; **일반** &#124; **추가 포함 디렉터리** 속성을 지정 된 `..\DIA SDK\include` 디렉터리입니다. 이렇게 하면 컴파일러가 dia2.h 파일을 찾을 수 있습니다.  
  
3.  에 **빌드** 메뉴를 클릭 하 여 **솔루션 다시 빌드**합니다.  
  
4.  Visual Studio를 닫습니다.  
  
#### <a name="to-run-the-sample"></a>이 샘플을 실행하려면  
  
1.  명령 프롬프트를 열고 다음을 입력 합니다.  
  
    ```  
    dia2dump filename  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [Dia2dump.cpp 소스 파일](../../debugger/debug-interface-access/dia2dump-cpp-source-file.md)   
 [Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드](../../porting/port-migrate-and-upgrade-visual-studio-projects.md)