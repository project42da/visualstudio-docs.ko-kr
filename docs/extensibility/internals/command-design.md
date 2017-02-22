---
title: "명령 디자인 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "명령"
  - "명령, 구현"
ms.assetid: 097108c3-f758-4b87-89d6-b32d12d9041a
caps.latest.revision: 34
caps.handback.revision: 34
ms.author: "gregvanl"
manager: "ghogen"
---
# 명령 디자인
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

있는 Vspackage에 명령을 추가 하는 경우 위치에 있습니다, 사용할 수 및이 처리 하는 방식을 지정 해야 합니다.  
  
## 명령 정의  
 새 명령을 정의할 수 VSPackage 프로젝트에 Visual Studio 명령을 테이블 \(.vsct\) 파일을 포함 합니다.  Visual Studio 패키지 템플릿을 사용 하 여 있는 Vspackage를 만든 경우 프로젝트에 이러한 파일 중 하나가 있습니다.  자세한 내용은 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)를 참조하십시오.  
  
 Visual Studio 명령을 표시할 수 있도록 되는 모든.vsct 파일을 병합 합니다.  이러한 파일이 이진 Vspackage에서 고유 하므로 Visual Studio 명령의 찾을 패키지를 로드할 수 없습니다.  자세한 내용은 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)를 참조하십시오.  
  
 Visual Studio 사용 하는 <xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> 등록 특성 메뉴 리소스와 명령을 정의 합니다.  자세한 내용은 [구현](../../extensibility/internals/command-implementation.md)를 참조하십시오.  
  
 명령 실행된 시에는 여러 가지 다른 방법으로 변경할 수 있습니다.  이들은 표시 또는 숨김, 설정 하거나 해제할 수 있습니다.  다른 텍스트 또는 아이콘을 표시 하거나 서로 다른 값이 포함 되어 있습니다.  Visual Studio 하면 VSPackage 로드 되기 전에 사용자 지정을 수행할 수 있습니다.  자세한 내용은 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)를 참조하십시오.  
  
## 명령 처리기  
 명령을 작성 하면 명령을 실행 하는 이벤트 처리기를 제공 해야 합니다.  사용자가 명령을 선택 하면 적절 하 게 라우팅할 수 있어야 합니다.  명령 라우팅을 활성화 또는 비활성화, 숨기기 또는 표시 및 실행 하도록 사용자가 선택 하는 경우에 올바른 Vspackage를 보낼 것입니다.  자세한 내용은 [라우팅 알고리즘](../../extensibility/internals/command-routing-algorithm.md)를 참조하십시오.  
  
## Visual Studio 명령 환경  
 Visual Studio Vspackages에 여러 호스팅하고 각 고유한 명령 집합을 제공할 수 있습니다.  해당 환경의 현재 작업에 해당 하는 명령만 표시 됩니다.  자세한 내용은 [가용성](../../extensibility/internals/command-availability.md) 및 [컨텍스트 개체 선택](../../extensibility/internals/selection-context-objects.md)을 참조하십시오.  
  
 새로운 명령, 메뉴, 도구 모음 또는 바로 가기 메뉴 정의 된 Vspackage에 설치할 때 네이티브 또는 관리 되는 어셈블리의 리소스를 참조 하는 레지스트리 항목을 통해 Visual Studio 해당 명령 정보를 제공 합니다.  각 리소스 다음 Visual Studio 명령을 테이블 \(.vsct\) 파일을 컴파일할 때 생성 되는 이진 데이터 리소스 \(.cto\) 파일을 참조 합니다.  이 모든 설치 된 VSPackage 로드 하지 않고도 병합된 명령 설정, 메뉴 및 도구 모음을 제공 합니다 Visual Studio 수 있습니다.  
  
### 명령 조직  
 환경 그룹, 우선 순위 및 메뉴에 명령을 배치합니다.  
  
-   그룹은 관련 명령 논리 그룹 예를 들어,  **컷**,  **복사**, 및  **붙여넣기** 명령 그룹.  그룹 메뉴에 표시 하는 명령입니다.  
  
-   개별 명령에서 그룹 메뉴에 나타나는 순서 대로 우선 순위를 결정 합니다.  
  
-   메뉴 그룹에 대 한 컨테이너 역할을 합니다.  
  
 환경 몇 가지 명령, 그룹, 및 메뉴를 미리 정의합니다.  자세한 내용은 [기본 명령, 그룹 및 도구 모음 배치](../../extensibility/internals/default-command-group-and-toolbar-placement.md)를 참조하십시오.  
  
 명령을 주 그룹으로 할당할 수 있습니다.  주 그룹 명령에서는 기본 메뉴 구조 및 위치 제어 있는  **사용자 지정** 대화 상자.  여러 그룹에서 명령을 나타나야 합니다. 예를 들어, 명령을 주 메뉴, 바로 가기 메뉴 및 도구 모음에서 수 있습니다.  자세한 내용은 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)를 참조하십시오.  
  
### 명령 라우팅  
 호출 및 Vspackages에 명령 라우팅 프로세스 개체 인스턴스에 대해 메서드를 호출 하는 프로세스와 다릅니다.  
  
 환경에서 현재 선택 영역을 기반으로 하는 순차적으로 안쪽의 \(로컬\) 명령 컨텍스트를 명령을 \(전역\)은 가장 바깥쪽 컨텍스트를 라우팅합니다.  명령을 실행할 수 있습니다 첫 번째 컨텍스트를 처리 하는 것입니다.  자세한 내용은 [라우팅 알고리즘](../../extensibility/internals/command-routing-algorithm.md)를 참조하십시오.  
  
 대부분의 경우에서 환경 명령을 사용 하 여 처리는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스입니다.  명령 라우팅 구성표 명령을 처리 하는 많은 다른 개체 수 있기 때문에 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 구현할 수 있는 개체의 수입니다. 여기에 Microsoft ActiveX 컨트롤, 창 보기 구현, 문서 개체, 프로젝트 계층 및 VSPackage 개체 자체 \(전역 명령\)에 포함 됩니다.  계층 구조에서 예를 들어, 라우팅 명령 일부 특수 한 경우에는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 인터페이스를 구현 해야 합니다.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[구현](../../extensibility/internals/command-implementation.md)|명령에 있는 Vspackage를 구현 하는 방법을 설명 합니다.|  
|[가용성](../../extensibility/internals/command-availability.md)|Visual Studio 컨텍스트에 사용할 수 있는 명령을 결정 하는 방법에 대해 설명 합니다.|  
|[라우팅 알고리즘](../../extensibility/internals/command-routing-algorithm.md)|Visual Studio 명령 라우팅 아키텍처 다른 Vspackages가 처리 해야 하는 명령을 활성화 하는 방법에 대해 설명 합니다.|  
|[배치 지침](../../extensibility/internals/command-placement-guidelines.md)|명령 Visual Studio 환경에서 배치 하는 것이 좋습니다.|  
|[Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)|Visual Studio 명령은 아키텍처 VSPackages 가장 잘 이용할 수 있습니다 하는 방법에 대해 설명 합니다.|  
|[기본 명령, 그룹 및 도구 모음 배치](../../extensibility/internals/default-command-group-and-toolbar-placement.md)|어떻게 Vspackages를 가장 잘 Visual Studio 포함 된 명령 사용 방법을 설명 합니다.|  
|[Vspackage를 관리합니다.](../../extensibility/managing-vspackages.md)|Visual Studio Vspackages를 로드 하는 방법에 대해 설명 합니다.|  
|[Visual Studio 명령 테이블 \(. Vsct\) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)|레이아웃 및 모양에 있는 VSPackages 명령에 설명 하는 데 사용 되는 XML 기반.vsct 파일에 대 한 정보를 제공 합니다.|