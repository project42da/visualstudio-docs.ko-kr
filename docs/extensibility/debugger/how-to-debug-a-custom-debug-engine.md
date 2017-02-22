---
title: "방법: 사용자 지정 디버그 엔진 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 하는 디버그 엔진"
  - "디버깅 [디버깅 SDK], 사용자 지정 디버그 엔진"
ms.assetid: df27a8d6-3938-45ff-b47f-b684e80b38a0
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: 사용자 지정 디버그 엔진 디버깅
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트 형식에서 디버그 엔진 \(DE\)을 시작 합니다.를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg.DebugLaunch%2A> 메서드가 있습니다.  이 의미는 DE가 제어 하는 인스턴스의 시작 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 형식을 제어 합니다.  그러나 해당 인스턴스를 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] DE는 디버깅할 수 없습니다.  가지를 사용자 지정 하는 DE 디버깅 하는 단계입니다.  
  
> [!NOTE]
>  : "디버깅는 사용자 지정 디버깅 엔진" 절차에 DE에 연결 하기 전에 시작 합니다에 대 한 기다려야 합니다.  DE은 시작 될 때 나타나는 사용자 DE 부분 메시지 상자를 배치 하면 해당 지점에 연결 하 고 계속 하려면 메시지 상자 선택을 취소 수 있습니다.  이렇게 하면 모든 catch 할 수 있습니다 DE 이벤트입니다.  
  
> [!WARNING]
>  원격 디버깅 다음 절차를 시도 하기 전에 설치 되어 있어야 합니다.  자세한 내용은 [원격 디버깅](../../debugger/remote-debugging.md)를 참조하십시오.  
  
### 사용자 지정 디버그 엔진 디버깅  
  
1.  Msvsmon.exe에서 원격 디버깅 모니터를 시작 합니다.  
  
2.  **도구** 메뉴에서 msvsmon.exe 선택  **옵션** 열은  **옵션** 대화 상자.  
  
3.  "인증 안 함" 옵션을 선택 하 고 클릭  **확인**.  
  
4.  인스턴스를 시작 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] DE 사용자 지정 프로젝트를 엽니다.  
  
5.  두 번째 인스턴스를 시작 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] DE를 시작 합니다. 사용자 정의 프로젝트 열기 및 \(개발 하는 경우 일반적으로 VSIP를 설치할 때 설정 되는 실험 레지스트리 하이브를 함\).  
  
6.  이 두 번째 인스턴스를 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]사용자 지정 프로젝트에서 소스 파일을 로드 하 고 디버깅할 프로그램을 시작 합니다.  로드 하거나 중단점이 적중 될 때까지 기다렸다가 DE 허용 하는 몇 분 정도 기다립니다.  
  
7.  첫 번째 인스턴스에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] \(DE 프로젝트와\) 선택  **프로세스에 연결** 에서  **디버그** 메뉴.  
  
8.  에 있는  **프로세스에 연결** 대화 상자에서 변경의  **전송** 에  **원격 \(네이티브 전용 인증 없음\)**.  
  
9. 변경의  **한정자** 시스템의 이름에 \(참고:이 이름에는 한 번만 입력 하면 되므로 항목 내역입니다.\).  
  
10. 에  **사용 가능한 프로세스** 목록에서 클릭 하 고 실행 중인 DE의 인스턴스는  **첨부** 단추.  
  
11. DE에서 기호를 로드 한 후에 DE 코드에 중단점을 삽입 합니다.  
  
12. 중지 하 고 디버깅 프로세스를 다시 시작 될 때마다 6\-10 단계를 반복 합니다.  
  
### 사용자 지정 프로젝트 형식 디버깅  
  
1.  시작 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 기본 레지스트리 하이브 및 부하에 프로젝트 \(이 경우, 원본 프로젝트 형식에서 프로젝트 형식에 인스턴스를\)를 입력 합니다.  
  
2.  프로젝트 속성을 열고 이동 하는  **디버그** 페이지입니다.  에  **명령**을, 경로를 입력의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE \(기본적으로,이입니다  *\[드라이브\]*\\Program Files\\Microsoft [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 8\\Common7\\IDE\\devenv.exe\).  
  
3.  에  **명령 인수**, 형식  `/rootsuffix exp` \(VSIP를 설치할 때 만든\)는 실험적인 레지스트리 하이브를.  
  
4.  **확인**을 클릭하여 변경 내용을 적용합니다.  
  
5.  프로젝트 형식 F5 키를 눌러 시작 합니다.  이 두 번째 인스턴스를 시작 합니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
6.  이 시점에서 프로젝트 형식이 소스 코드에서 중단점을 배치할 수 있습니다.  
  
7.  두 번째 인스턴스를 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 로드 또는 프로젝트 형식의 새 인스턴스를 만듭니다.  로드 하거나 만드는 동안 중단점을 적중 수 있습니다.  
  
8.  프로젝트 형식을 디버깅 합니다.  
  
9. DE를 실행 하는 프로세스를 디버그 하면 실행 된 후에 DE를 연결 하는 "디버깅는 사용자 지정 디버깅 엔진" 절차에서 단계를 수행할 수 있습니다.  이 세 가지 인스턴스를 제공 합니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 실행: 소스 프로젝트 형식, 두 번째 인스턴스화된 프로젝트 형식 및 사용자 DE에 연결 된 제 3의 하나.  
  
## 참고 항목  
 [사용자 지정 디버그 엔진 만들기](../../extensibility/debugger/creating-a-custom-debug-engine.md)