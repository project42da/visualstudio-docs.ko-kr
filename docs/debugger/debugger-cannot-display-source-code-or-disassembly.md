---
title: "디버거에서 소스 코드나 디스어셈블리를 표시할 수 없습니다 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: disassembly code, errors
ms.assetid: 112d3ea3-fdd2-4bce-92b4-167a76258934
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8795ee33a5fc96c979cb67636d3ce5dd23c1b665
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="debugger-cannot-display-source-code-or-disassembly"></a>디버거가 현재 위치에 대한 소스 코드나 디스어셈블리를 표시할 수 없습니다.
이 오류의 의미는 다음과 같습니다.  
  
 실행이 중지된 현재 위치에 대한 소스 코드나 디스어셈블리를 디버거에서 표시할 수 없습니다.  
  
 이 오류 메시지의 원인은 다음과 같습니다.  
  
-   디스어셈블리를 지원하지 않는 언어를 디버깅하는 동안 소스 코드가 없는 위치에서 중단점이 적중되었을 수 있습니다. 열기는 **중단점** 창에서 중단점을 찾아 삭제 합니다.  
  
-   스크립트를 디버깅하는 경우 프로그램에 스레드가 없을 때 중단점이 적중되었을 수 있습니다. 선택 **단계** 또는 **계속** 에서 **디버그** 메뉴 디버깅을 다시 시작 합니다.  
  
-   보안상의 이유로, 디버깅하고 있는 프로그램에서 디버거가 스택, 스레드, 레지스터 및 기타 컨텍스트 정보를 읽지 못할 수 있습니다. 이러한 오류는 가상 디렉터리에 대한 올바른 액세스 권한 없이 웹 응용 프로그램을 디버깅하는 경우에 발생합니다. 가상 디렉터리의 보안 권한을 Anonymous로 설정하고 다시 시도하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio의 디버깅](../debugger/index.md) [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)   
 [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)