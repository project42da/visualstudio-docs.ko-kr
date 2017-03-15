---
title: "VSPackage 등록 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Vspackage 등록"
  - "Vspackage를 등록 하는 중"
ms.assetid: ecd20da8-b04b-4141-a8f4-a2ef91dd597a
caps.latest.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 18
---
# VSPackage 등록
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Vspackage advise 해야 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 은 설치 되어 있고 해야 로드할 수 있습니다. 레지스트리에서 정보를 작성 하 여이 프로세스를 수행 합니다. 설치 관리자의 일반적인 작업입니다.  
  
> [!NOTE]
>  자동 등록을 사용 하 여 VSPackage 개발 하는 동안이 허용 되는 좋습니다. 그러나 [!INCLUDE[vsipprvsip](../../extensibility/includes/vsipprvsip_md.md)] 파트너를 자사 제품 설치의 일부로 자체 등록을 사용 하 여 제공할 수 없습니다.  
  
 Windows Installer 패키지에 대 한 레지스트리 항목 레지스트리 테이블에서 일반적으로 수행 됩니다. 또한 레지스트리 테이블의 파일 확장명을 등록할 수 있습니다. 그러나 Windows Installer ProgId \(프로그래밍 식별자\), 클래스, 확장 및 동사 테이블을 통해 기본 제공 지원을 제공합니다. 자세한 내용은 참조 [데이터베이스 테이블](http://msdn.microsoft.com/library/aa368259\(VS.85\).aspx)합니다.  
  
 레지스트리 항목 선택한 side\-by\-side\-전략에 적합 한 구성 요소와 연결 되도록 해야 합니다. 예를 들어, 공유 파일에 대 한 레지스트리 항목은 해당 파일의 Windows Installer 구성 요소와 연결 해야 합니다. 마찬가지로, 버전별 파일에 대 한 레지스트리 항목은 해당 파일의 구성 요소와 연결 해야 합니다. 그렇지 않으면을 설치 하거나 제거의 특정 버전에 대해 VSPackage [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다른 버전에서 VSPackage를 손상 시킬 수 있습니다. 자세한 내용은 [여러 버전의 Visual Studio 지원](../../extensibility/supporting-multiple-versions-of-visual-studio.md)을 참조하세요.  
  
> [!NOTE]
>  등록을 관리 하는 가장 쉬운 방법은 개발자 등록 및 설치 시 등록에 대 한 동일한 파일에서 동일한 데이터를 사용 하는 경우 예를 들어 일부 installer 개발 도구는 빌드 시 형식의.reg 파일을 사용할 수 있습니다. 개발자가 자신의 일상적인 개발을 위해.reg 파일을 유지 하 고 디버깅, 동일한 파일에에서 포함 될 수는 설치 관리자 자동으로 합니다. 자동으로 등록 데이터를 공유할 수 없다면, 설치 프로그램의 사본을 등록 데이터가 최신 인지 확인 해야 합니다.  
  
## 관리 되지 않는 VSPackages를 등록 하는 중  
 ATL 스타일.rgs 파일 등록 정보를 저장을 사용 하는 관리 되지 않는 Vspackage \(Visual Studio 패키지 템플릿에 의해 생성 된 포함\). .Rgs 파일 형식은 ATL 되며 일반적으로 사용할 수 없습니다\-제작 도구는 설치 하는 것입니다. VSPackage 설치 관리자에 대 한 등록 정보는 별도로 유지 되어야 합니다. 예를 들어 개발자가 파일을 보관할 수.reg 형식에서.rgs 동기화 파일 변경. .Reg 파일을 개발 작업에 대 한 RegEdit와 병합 또는 설치 관리자에서 사용할 수 있습니다.  
  
## 관리 되는 VSPackages를 등록 하는 중  
 RegPkg 도구 관리 되는 VSPackage에서 등록 특성 읽고 정보 레지스트리 또는 설치 프로그램을 통해 사용할 수 있는 쓰기.reg 서식 파일에 직접 작성할 수 중 하나입니다.  
  
> [!NOTE]
>  RegPkg 도구 재배포 가능 패키지 되지 않으며 사용자의 시스템에 VSPackage 등록에 사용할 수 없습니다.  
  
## 왜 Vspackage 등록 하지 않아야 자체 설치 시간  
 사용자 VSPackage 설치 관리자를 사용 하 여 자체 등록에 의존 하지 마십시오. 얼핏 보기에 VSPackage 자체에 VSPackage의 레지스트리 값을 유지 좋은 생각 처럼 보입니다. 개발자가 일상적인 작업에 사용할 수 있는 레지스트리 값이 필요 하 고 테스트 하면 설치 관리자에서 레지스트리 데이터의 개별 복사본을 유지 관리 하지 않아도 제공 합니다. 설치 관리자는 자체 레지스트리 값을 쓸 VSPackage에 사용할 수 있습니다.  
  
 이론적으로는 좋지만, 자체 등록에 VSPackage 설치에 대 한 적절 하지 않을 수 있는 몇 가지 결점이 있습니다.  
  
-   올바르게 설치, 제거, 설치 롤백 및 제거 rollback을 지 원하는 자체 RegPkg를 호출 하 여 등록 된 모든 관리 되는 VSPackage에 대 한 4 개의 사용자 지정 작업을 제작 하는 데 필요 합니다.  
  
-   네 번째 사용자 지정 작업 RegSvr32 또는 RegPkg의 지원 되는 모든 버전에 대 한 호출을 제작 하는 병렬\-지원 방법이 필요할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
-   자체 등록 된 모듈을 설치의 다른 기능 또는 응용 프로그램에서 자동으로 등록된 키가 사용 하는 경우 알리는 방법이 없기 때문에 다시 안전 하 게 롤백할 수 없습니다.  
  
-   자체 등록 된 Dll 때로는 존재 하지 않거나 잘못 된 버전 보조 Dll에 연결 합니다. 반면에 Windows Installer는 시스템의 현재 상태에 의존 하지 않고 레지스트리 테이블을 사용 하 여 Dll을 등록할 수 있습니다.  
  
-   형식 라이브러리와 같은 네트워크 리소스에 대 한 액세스 구성 요소는 둘 다 지정으로 원본에서 실행 되 고 SelfReg 테이블에 나열 됩니다 자동 등록 코드를 정의할 수 있습니다. 이렇게 하면 관리자 설치 중에 실패 하는 구성 요소를 설치 합니다.  
  
## 참고 항목  
 [Windows Installer](http://msdn.microsoft.com/library/cc185688\(VS.85\).aspx)   
 [Managed Package Registration](http://msdn.microsoft.com/ko-kr/f69e0ea3-6a92-4639-8ca9-4c9c210e58a1)