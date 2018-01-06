---
title: "테스트 영역 8: 플러그 인 전환 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control [Visual Studio SDK], switching plug-ins
- source control plug-ins, switching
ms.assetid: 01370792-b5da-4e46-9ce2-7dd326587141
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9f6a518d618b3a98ec85cbbe015d3b2c5fc7a710
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="test-area-8-plug-in-switching"></a>테스트 영역 8: 플러그 인 전환
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE) 현재 소스 제어 플러그 인을 변경 하려면 사용자 인터페이스 (UI)에 있습니다. 이 테스트 영역을 선택 하는 솔루션 소스 제어에 사용할 플러그 인 프로세스에 대 한 테스트 사례를 제공 합니다.  
  
## <a name="command-menu-access"></a>명령 메뉴 액세스  
 다음 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 메뉴 경로 테스트 사례에서 사용 됩니다.  
  
-   현재 소스 제어 플러그 인: **도구** -> **옵션** -> **소스 제어** -> **플러그 인 선택** .  
  
-   변경 소스 제어 바인딩이: **파일** -> **소스 제어** -> **소스 제어 변경**...  
  
## <a name="common-expected-behavior"></a>예상 되는 일반적인 동작  
 Visual Studio를 종료 하거나 솔루션을 다시 로드 하지 않고 솔루션에 대 한 플러그 인 소스 제어 변경 불가능 합니다. 또한 현재 소스 제어 플러그 인 해당 솔루션 로드 되 면 솔루션에서 사용 하는 자동으로 변경 합니다.  
  
## <a name="test-cases"></a>테스트 사례  
 플러그 인 전환 테스트 영역에 대 한 특정 테스트 사례는 다음과 같습니다.  
  
### <a name="case-8a-automatic-change"></a>8a 대/소문자: 자동 변경  
  
#### <a name="expected-behavior"></a>예상 되는 동작  
 사용자가 소스 제어에서 사용 중인 솔루션 로드 될 때 솔루션은 자동으로 로드 하 고 적절 한 소스 제어 플러그 인 최신 선택 됩니다.  
  
|작업|테스트 단계|예상된 결과를 확인합니다|  
|------------|----------------|--------------------------------|  
|자동 소스 제어 플러그 인 변경|1.  현재로 테스트에서 플러그 인 선택 (**도구** -> **옵션** -> **소스 제어** -> **플러그 인 선택 영역**.)<br />2.  새 프로젝트를 만듭니다.<br />3.  소스 제어에 솔루션을 추가 합니다.<br />4.  또 다른 플러그 인 선택 (예를 들어 [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)]).<br />5.  언로드하여 솔루션 프롬프트를 허용 합니다.<br />6.  디스크에서 솔루션을 다시 엽니다.|솔루션은 열립니다.<br /><br /> 테스트 중인 플러그인은 현재 소스 제어 플러그 인 합니다.|  
  
### <a name="case-8b-solution-based-change"></a>8b 대/소문자: 솔루션을 기반으로 변경  
  
#### <a name="expected-behavior"></a>예상 되는 동작  
 솔루션에는 해당 연결 된 소스 제어 플러그 인 변경 있을 수 있습니다.  
  
|작업|테스트 단계|예상된 결과를 확인합니다|  
|------------|----------------|--------------------------------|  
|솔루션에 대 한 플러그인 변경|1.  현재로 테스트에서 플러그 인 선택 (**도구** -> **옵션** -> **소스 제어** -> **플러그 인 선택 영역**).<br />2.  새 프로젝트 및 솔루션을 만듭니다.<br />3.  소스 제어에 솔루션을 추가 합니다.<br />4.  소스 제어에서 솔루션을 바인딩 해제 (사용 하 여 **소스 제어 변경** 대화 상자).<br />5.  또 다른 플러그 인 선택 (예를 들어 [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)]).<br />6.  언로드된 디스크에서 솔루션을 다시 로드 하십시오.<br />7.  소스 제어에 솔루션을 추가 합니다.<br />8.  소스 제어에서 솔루션을 바인딩 해제 (사용 하 여 **소스 제어 변경** 대화 상자).<br />9. 테스트 다시 대상 플러그 인을 선택 합니다.<br />10. 언로드된 디스크에서 솔루션을 다시 로드 하십시오.<br />11. 솔루션을 원래 위치로 바인딩합니다 (사용 하는 **소스 제어 변경** 대화 상자).|선택한를 사용 하 여 소스 제어에 솔루션 추가 플러그 인 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인에 대한 테스트 가이드](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)