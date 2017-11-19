---
redirect_url: shell/visual-studio-shell-integrated
title: "Visual Studio Shell (통합) | Microsoft Docs"
ms.custom: 
ms.date: 02/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio shell, integrated mode features
- Shell [Visual Studio], integrated mode features
ms.assetid: 0b40d495-f17f-4bb9-ace8-b365a7172784
caps.latest.revision: "26"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0d92a6c7250e22972a2b352b74b974601ff6065c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-shell-integrated"></a>Visual Studio Shell (통합)
통합 하는 Visual Studio shell에 통합된 개발 환경 (IDE), 디버거 및 소스 제어 통합에 포함 됩니다. 프로그래밍 언어가 포함 됩니다. 하지만 integrated shell에 프로그래밍 언어를 추가할 수 있습니다 하는 프레임 워크를 제공 합니다.  
  
 통합 하는 Visual Studio shell에 통합된 셸 특정 구성 요소를 포함 하는 추가 설치는 Visual Studio 격리 셸의 조합 실제로입니다.  통합된 셸 응용 프로그램 모두는 격리 셸에서 재배포 가능 패키지를 포함 해야 [Microsoft Visual Studio Shell (격리) 재배포 가능 패키지](http://go.microsoft.com/fwlink/?LinkId=616022) 통합된 shell 재배포 가능 패키지 뿐만 아니라 [Microsoft Visual Studio 셸 (통합된) 재배포 가능 패키지](http://go.microsoft.com/fwlink/?LinkId=616021)합니다.  
  
> [!NOTE]
>  분리 되 고 통합 셸 재배포 가능 패키지에 액세스 하기 전에 한 간략 한 고객 설문 조사 해야 합니다.  설문 조사를 채운 후에 재배포 가능 패키지 다운로드 링크는 Visual Studio 연결 페이지로 이동 합니다.  아래에서 Visual Studio Connect 사이트에 대 한 후속 방문에서 다운로드 링크를 찾을 수 있습니다는 **프로그램 &#124; VISUAL STUDIO 2015 통합 및 ISOLATED SHELL** 탭 합니다.  
  
 전체 버전의 Visual Studio와 같은 컴퓨터에 통합된 셸 응용 프로그램을 설치 하는 경우 응용 프로그램의 구성 요소는 Visual Studio에 직접 통합 됩니다.  
  
## <a name="features-in-the-integrated-shell"></a>Integrated Shell의 기능  
  
|||  
|-|-|  
|기능 영역|기능|  
|언어 지원|-없음|  
|IDE|<ul><li>설정<br /><br /> <ul><li>설정 만들기</li><li>설정 가져오기 및 내보내기</li><li>다시 설정</li></ul></li><li>**도구 상자** 통합</li><li>**작업 목록** 통합</li><li>도움말 통합</li><li>**옵션** 대화 상자</li><li>글꼴 및 색 관리</li><li>**출력** 창</li><li>**명령** 창</li><li>창 관리</li><li>명령, 메뉴 및 키 바인딩</li><li>도메인 특정 언어 (DSL) 런타임</li></ul>|  
|프로젝트 시스템 및 프로젝트 형식|-솔루션과 솔루션 폴더<br />-솔루션 구성 관리자<br />-항목 관리<br />-단일 프로젝트 및 다중 프로젝트 솔루션<br />-응용 프로그램 디자이너 (간소화 된 프로젝트 속성)<br />-웹 참조를 추가 합니다.<br />-서비스 참조를 추가 합니다.<br />-단일 프로젝트<br />-웹 사이트 프로젝트 형식<br />-웹 응용 프로그램 프로젝트|  
|빌드|-IDE에서 사용자 지정 빌드 단계<br />-(IP) 지적 재산 보호에 대 한 미리 컴파일<br />-코드 서명<br />     MSBuild|  
|편집기|-코드 (통합된 찾기, 원본 정의 inheritance) 도구를 검색 합니다.<br />코드 탐색<br />-IntelliSense<br />-스마트 태그<br />-리팩터링<br />-서식이 다시 적용<br />-IntelliSense 필터링<br />-   **코드 정의** 창|  
|Designer|Windows Presentation Foundation 디자이너<br />Windows Forms 디자이너<br />-웹 디자이너 및 HTML 편집기|  
|데이터|-   **서버 탐색기** (간체: 데이터만). 참고 1을 참조하세요.<br />-   **데이터 원본** 창<br />-전체 집합이 데이터 컨트롤<br />XML 편집기<br />로컬 데이터 소스에 데이터 바인딩 (합니다. MDF 또는 합니다. MDB)<br />개체에 데이터 바인딩<br />웹 서비스에 데이터 바인딩<br />로컬 데이터베이스 서버에 데이터 바인딩<br />원격 데이터베이스 서버에 데이터 바인딩<br />원격 데이터에 대 한 DDL 도구<br />-   **서버 탐색기** 확장성 ([!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 샘플)|  
|디버거|-로컬 디버깅 합니다. 참고 2 참조 하십시오.<br />관리 디버깅<br />-로컬 디버깅<br />-로컬 프로세스에 연결 합니다.<br />-원격 프로세스에 연결 합니다.<br />아닌 익명이 대리자<br />-응용 프로그램 도메인<br />-ASPX 디버깅<br />-특성<br />-Func eval 하는 동안 중단 합니다.<br />-중단점<br />-중단점 제약 조건<br />-호출 스택<br />-   **명령** 창<br />-크로스 스레드 디버깅<br />데이터 팁<br />데이터 시각화 도우미<br />관리 디버깅 도우미 (Mda)에 대 한 디버거 지원<br />형식 전달자에 대 한 디버거 지원<br />-DTEEvents OTB에 대 한 지원<br />-JMC 스텝 퍼<br />-디버거 AppID 테스트 (DBGCLR)<br />-디버거 프로필<br />-디버거 도구 및 옵션<br />--반복기를 디버깅 하는 중<br />-디자인 타임 식 계산<br />-C# 식 계산기<br />-디스어셈블리<br />-편집 하며 계속 하기<br />식 계산기 windows (조사식, 지역, 자동)<br />-예외 도우미<br />-예외<br />-실행<br />-   제네릭<br />-오른쪽 소스 가져오기<br />-HPC/클러스터 디버깅<br />-다중 언어 디버깅 통합<br />-InterOp 디버깅<br />--Just-in-time 디버깅<br />-로컬 디버깅<br />관리 디버깅<br />-수동 제어 (프로세스 창)<br />메모리<br />-미니 덤프 지원<br />-모듈<br />-다중 프로세스 디버깅<br />-네이티브 디버깅<br />-새 디버그 엔진 지원<br />-최적화 된 코드 디버깅<br />-출력 창을 필터링<br />-처리 호스팅 관리 되는 디버깅에 대 한<br />-프로세스<br />-간략 한 조사식<br />-등록<br />-레지스터 스택에<br />-원격 디버깅<br />-값을 반환 합니다.<br />스크립트 디버깅<br />소스 서비스 지원<br />-보안<br />---나란히<br />-SQL<br />-기호 서버<br />추적 지점<br />스레드<br />-시각화<br />-Extensible Stylesheet Language Transformations (XSLT) 디버거|  
|64 비트 지원|-관리 / 네이티브 코드에서 모든 언어에 대 한 64 비트 디버깅<br />-네이티브 x64 지원|  
|소스 코드 제어 (SCC)|-기본 SCC 통합 합니다. 참고 3을 참조하세요.<br />-도구 옵션 확인|  
|확장성|--Vspackage 및 MEF 구성 요소를 사용 하는 중|  
  
## <a name="notes"></a>참고  
  
#### <a name="1-data-tools"></a>1. 데이터 도구  
 데이터 확장성 지원 및 단순한와 같은 데이터베이스 개발 도구를 포함 하는 통합된 셸 **솔루션 탐색기**합니다. 그러나 SQL Server Express, SQL 보고 및 Crystal Reports integrated shell에 제외 됩니다.  
  
#### <a name="2-debugging-support"></a>2. 디버깅 지원  
 Integrated shell 커뮤니티 버전의 Visual Studio에 포함 된 동일한 디버깅 엔진을 포함 합니다. 디버깅 엔진 실행, 연결, 중단점 설정, 편집 하며 계속 하기, 다른 사용자와 같은 관리 코드 및 관련된 기능에 대 한 공용 디버거를 포함 합니다. 그러나 디버깅 엔진은 SQL Server 데이터베이스 디버깅을 지원 하지 않습니다.  
  
 하지만 지원 추가 언어를 지원 하도록 확장할 수 없습니다 기본 디버거 패키지에 포함 된 네이티브 디버깅에 대 한 합니다.  
  
#### <a name="3-source-code-control-integration"></a>3. 소스 코드 제어 통합  
 Integrated shell MSSCCI 기반 일반적인 소스 제어 통합 구성 요소를 제공 하는 데 및 소스 코드 제어 (SCC)를 구현 하기 위한 Api를 제공 합니다.  
  
 SCC 통합 Pro 버전의 Visual Studio의 일반 기능 하지는 않지만 SCC 통합 integrated shell에 제공 됩니다.  
  
#### <a name="4-build-support"></a>4. 빌드 지원  
 Integrated shell 빌드 지원을 제공합니다. 빌드에 대 한 정보를 찾을 수 있습니다는 [MSBuild 참조](../msbuild/msbuild-reference.md)합니다.  
  
## <a name="features-not-included-in-the-integrated-shell"></a>Integrated Shell에 포함 되지 않은 기능  
 다음은 integrated shell에 포함 되지 않는 기능의 목록입니다.  
  
-   클래스 디자이너  
  
-   [선점형 보호-Dotfuscator](../ide/dotfuscator/index.md)  
  
-   언어 기능  
  
-   VSHost  
  
-   Visual Studio 언어가 없습니다 또는 관련 된 프로젝트 템플릿 또는 프로젝트 항목 템플릿 integrated shell에 포함 됩니다. 다른 기능의 언어별 구현이 없습니다 예제에서는 Visual Basic 코드 조각에 포함 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)