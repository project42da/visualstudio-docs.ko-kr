---
title: "방법:.NET Framework 소스 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 02/23/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging, .NET Framework source
ms.assetid: fc12e472-ac6a-4e77-8e22-a769e13a03b8
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 75f3665afcf5d4937fae46e2a6871e0f7121b561
ms.sourcegitcommit: 342e5ec5cec4d07864d65379c2add5cec247f3d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2018
---
# <a name="how-to-debug-net-framework-source"></a>방법: .NET Framework 소스 디버깅
.NET Framework 소스를 디버깅 하려면 코드에 대 한 디버깅 기호에 액세스할 수 있어야 합니다. 또한.NET Framework 소스를 한 단계씩를 사용 하도록 설정 해야 합니다.  
  
 .NET Framework를 사용할 수 단계별 실행 및 기호 다운로드에 **옵션** 대화 상자. 기호 다운로드를 설정할 때 기호를 즉시 다운로드할 수도 있고 나중에 다운로드하도록 옵션만 설정해 놓을 수도 있습니다. 기호를 즉시 다운로드하지 않으면 기호는 다음 번에 응용 프로그램 디버깅을 시작할 때 다운로드됩니다. 다운로드 하 여 수동으로 수행할 수는 **모듈** 창 또는 **호출 스택** 창.  
  
### <a name="to-enable-net-framework-source-debugging"></a>.NET Framework 소스 디버깅을 사용하려면  
  
1.  에 **도구** 메뉴를 클릭 하 여 **옵션**s입니다.  
  
2.  에 **옵션** 대화 상자를 클릭는 **디버깅** 범주입니다.  
  
3.  에 **일반** 상자에서 설정 **사용 하도록 설정 하는.NET Framework 소스 단계별 실행 합니다.**  
  
    1.  내 코드만을 사용하는 경우에는 내 코드만을 이제 사용하지 않는다는 경고 대화 상자가 표시됩니다. **확인**을 클릭합니다.  
  
    2.  기호 캐시 위치가 설정되어 있지 않으면 기본 기호 캐시 위치가 이제 설정된다는 또 다른 경고 대화 상자가 표시됩니다. **확인**을 클릭합니다.  
  
4.  아래는 **디버깅** 범주를 클릭 하 여 **기호**합니다.  
  
5.  기호 캐시 위치를 변경 하려는 경우에서 위치를 편집 **이 디렉터리의 기호 캐시** 키를 누르거나 **찾아보기** 위치를 선택 합니다.  
  
6.  기호를 즉시 다운로드 하려면 클릭 **기호 로드를 사용 하 여 위의 위치**합니다.  
  
     이 단추를 디자인 모드에서 사용할 수 있지만 디버깅 하는 동안 사용할 수 있습니다.  
  
     지금 기호를 다운로드하도록 선택하지 않으면 다음 번 프로그램 디버깅을 시작할 때 기호가 자동으로 다운로드됩니다.  
  
7.  **확인**을 클릭하여 **옵션** 대화 상자를 닫습니다.  
  
### <a name="to-load-framework-symbols-using-the-modules-window"></a>모듈 창을 사용하여 Framework 기호를 로드하려면  
  
1.  에 **모듈** 창 (디버깅 하는 동안 선택 **디버그** > **Windows** > **모듈**), 기호가 로드 되지 않은 모듈을 마우스 오른쪽 단추로 클릭 합니다. 확인할 수 있습니다 기호가 로드 되었는지 확인 하 여 하지는 **기호 상태** 열입니다.  
  
2.  가리킨 **기호 설정** 클릭 **Microsoft 기호 서버** Microsoft 공용 기호 서버에서 기호를 다운로드 하도록 합니다. 또는 모듈을 마우스 오른쪽 단추로 클릭 하 고 선택할 수 **기호 로드** 기호를 이전에 저장 되어 있는 디렉터리에서 로드 합니다.  
  
### <a name="to-load-framework-symbols-using-the-call-stack-window"></a>호출 스택 창을 사용하여 Framework 기호를 로드하려면  
  
1.  에 **호출 스택** 창에서 기호가 로드 되지 않은 프레임을 마우스 오른쪽 단추로 클릭 합니다. 프레임이 흐리게 표시됩니다.  
  
2.  가리킨 **기호 설정** 클릭 **Microsoft 기호 서버**, 또는 모듈을 마우스 오른쪽 단추로 클릭 하 고 선택 **기호 경로**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Debugging Managed Code](../debugger/debugging-managed-code.md) (관리 코드 디버그)  
 [기호 (.pdb)을 지정 하 고 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)