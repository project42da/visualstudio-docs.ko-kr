---
title: "방법: 디버깅 하는 사용자 지정 디버그 엔진 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, debugging
- debugging [Debugging SDK], custom debug engines
ms.assetid: df27a8d6-3938-45ff-b47f-b684e80b38a0
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6a91dbb7797d69ec71b776eeef5e34e0ced21ad9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-debug-a-custom-debug-engine"></a>방법: 디버깅 하는 사용자 지정 디버그 엔진
디버그 엔진 (DE)를 시작 하는 프로젝트 형식에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg.DebugLaunch%2A> 메서드. 즉, 인스턴스의 제어는 DE가 시작 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 형식을 제어 합니다. 그러나의 해당 인스턴스에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 는 DE를 디버깅할 수 없습니다. 다음은 사용자 지정 사용자 DE 디버깅할 수 있도록 하는 단계입니다.  
  
> [!NOTE]
>  : "디버깅는 사용자 지정 디버그 엔진" 절차에서 연결할 수 있는 전에 시작할 DE 대기 해야 합니다. 시작 부분에서 DE 시작 될 때 나타나는 프로그램 DE 메시지 상자를 배치 하는 경우 해당 시점에 연결할 수 있으며 계속 하려면 메시지 상자의 선택을 취소 한 다음 수 있습니다. 이런 방식으로 catch 할 수 있습니다 모든 DE 이벤트입니다.  
  
> [!WARNING]
>  다음 절차를 시도 하기 전에 설치 된 원격 디버깅 하는 것이 있어야 합니다. 참조 [원격 디버깅](../../debugger/remote-debugging.md) 대 한 자세한 내용은 합니다.  
  
### <a name="debugging-a-custom-debug-engine"></a>사용자 지정 디버그 엔진 디버깅  
  
1.  원격 디버깅 모니터 인 msvsmon.exe를 시작 합니다.  
  
2.  **도구** msvsmon.exe, 메뉴 **옵션** 열려는 **옵션** 대화 상자.  
  
3.  "인증 안 함" 옵션을 선택 하 고 클릭 **확인**합니다.  
  
4.  인스턴스를 시작 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자 지정 DE 프로젝트를 엽니다.  
  
5.  두 번째 인스턴스를 시작 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 는 DE를 시작 하 여 사용자 지정 프로젝트를 엽니다 (개발의 경우이 일반적으로 VSIP 설치 될 때 설정 된 실험 레지스트리 하이브에서).  
  
6.  이 두 번째 인스턴스에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 사용자 지정 프로젝트에서 소스 파일을 로드 하 고 프로그램을 디버깅할 수 있습니다. 로드 하거나 중단점이 적중 될 때까지 기다립니다 DE 허용 하 고 있습니다.  
  
7.  첫 번째 인스턴스에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (DE 프로젝트)를 선택 **프로세스에 연결** 에서 **디버그** 메뉴.  
  
8.  에 **프로세스에 연결** 대화 상자에서 변경 된 **전송** 를 **원격 (네이티브만 인증 안 함)**합니다.  
  
9. 변경 된 **한정자** 컴퓨터의 이름으로 (참고:이 이름에 한 번만 입력 해야 할 항목의 기록을 이므로).  
  
10. 에 **사용 가능한 프로세스** 목록에서 실행 중 이며 클릭 하 여 DE 인스턴스 선택의 **연결** 단추입니다.  
  
11. 프로그램 DE에서 기호 로드 후 DE 코드에 중단점을 삽입 합니다.  
  
12. 중지 하 고 다음 디버깅 프로세스를 다시 시작 될 때마다 6-10 단계를 반복 합니다.  
  
### <a name="debugging-a-custom-project-type"></a>사용자 지정 프로젝트 형식을 디버깅  
  
1.  시작 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 일반 레지스트리 하이브 및 부하에 프로젝트 (이것은, 원본으로 사용할 프로젝트 형식, 프로젝트 형식의 인스턴스화 하지)을 입력 합니다.  
  
2.  프로젝트 속성을 열고로 이동 된 **디버그** 페이지. 에 대 한는 **명령**, 경로를 입력는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE (기본적으로이 *[드라이브]*files\microsoft [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 8\Common7\IDE\devenv.exe).  
  
3.  에 대 한는 **명령 인수**, 형식 `/rootsuffix exp` 실험 레지스트리 하이브에서 (VSIP를 설치할 때 만든)에 대 한 합니다.  
  
4.  **확인** 을 클릭하여 변경 내용을 수락합니다.  
  
5.  F5 키를 눌러 프로젝트 형식을 시작 합니다. 동시에 시작 됩니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
6.  이 시점에서 프로젝트 형식 소스 코드에서 중단점을 배치할 수 있습니다.  
  
7.  두 번째 인스턴스에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 로드 하거나 프로젝트 형식의 새 인스턴스를 만듭니다. 로드 또는 만드는 동안 중단점을 적중 될 수 있습니다.  
  
8.  프로젝트 형식을 디버깅 합니다.  
  
9. DE 시작한의 프로세스를 디버깅 하려는 경우를 시작한 후 사용자 DE 연결할 "디버깅는 사용자 지정 디버그 엔진" 절차의 단계를 수행할 수 있습니다. 이렇게 하면의 세 인스턴스 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 실행: 프로젝트 형식이 소스, 인스턴스화된 프로젝트 형식 및 프로그램 DE에 연결 된 제 3 초에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 디버그 엔진 만들기](../../extensibility/debugger/creating-a-custom-debug-engine.md)