---
title: "디자인 명령 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands
- commands, implementation
ms.assetid: 097108c3-f758-4b87-89d6-b32d12d9041a
caps.latest.revision: "34"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fe3db0582c65a2ece2162ab24afb6d179b865a27
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="command-design"></a>명령 디자인
VSPackage에 명령을 추가할 때 표시 될 위치를 사용할 수 있으면 하 고 처리 하는 방법 지정 해야 합니다.  
  
## <a name="defining-commands"></a>명령 정의  
 새 명령을 정의 하려면 VSPackage 프로젝트에 Visual Studio 명령 테이블 (.vsct) 파일을 포함 합니다. Visual Studio 패키지 템플릿을 사용 하 여 VSPackage를 만든 경우 프로젝트는 이러한 파일 중 하나에 포함 됩니다. 자세한 내용은 참조 [Visual Studio 명령 테이블 (합니다. Vsct) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)합니다.  
  
 Visual Studio 명령을 표시할 수 있도록 찾으면 모든.vsct 파일을 병합 합니다. 이러한 파일에서 이진 VSPackage 구별 되므로 Visual Studio가 명령을 찾기 위해 패키지를 로드할 필요가 없습니다. 자세한 내용은 참조 [어떻게 Vspackage 추가 사용자 인터페이스 요소](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)합니다.  
  
 Visual Studio를 사용 하 여는 <xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> 등록 특성을 메뉴 리소스 및 명령을 정의 합니다. 자세한 내용은 참조 [구현](../../extensibility/internals/command-implementation.md)합니다.  
  
 명령은 여러 가지 다른 방법으로 런타임 시 변경할 수 있습니다. 있습니다 수 표시 또는 숨김, 설정 하거나 해제할 수 있습니다. 다른 텍스트 또는 아이콘을 표시 하거나 다른 값이 들어 수 있습니다. Visual Studio VSPackage를 로드 하기 전에 다양 한 사용자 지정을 수행할 수 있습니다. 자세한 내용은 참조 [어떻게 Vspackage 추가 사용자 인터페이스 요소](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)합니다.  
  
## <a name="command-handlers"></a>명령 처리기  
 명령을 만들 때 명령을 실행 하는 이벤트 처리기를 제공 해야 합니다. 사용자가 명령을 선택, 적절 하 게 라우팅해야 합니다. 명령 라우팅 사용 또는 사용 하지 않도록, 숨기기 또는 표시 및 사용자가 작업을 수행 하도록 선택한 경우 실행 하기 위해 올바른 VSPackage를 보내는 의미 합니다. 자세한 내용은 참조 [라우팅 알고리즘](../../extensibility/internals/command-routing-algorithm.md)합니다.  
  
## <a name="the-visual-studio-command-environment"></a>Visual Studio 명령 환경  
 Visual Studio Vspackage, 개수에 관계 없이 호스트 하 고 각 명령 집합 자체를 느려지게 할 수 있습니다. 환경을 사용 중인 현재 작업에 적합 한 명령만 표시 합니다. 자세한 내용은 참조 [가용성](../../extensibility/internals/command-availability.md) 및 [컨텍스트 개체 선택](../../extensibility/internals/selection-context-objects.md)합니다.  
  
 새 명령, 메뉴, 도구 모음 또는 바로 가기 메뉴를 정의 하는 VSPackage 네이티브 또는 관리 되는 어셈블리에 리소스를 참조 하는 레지스트리 항목을 통해 설치 중에 Visual Studio에 명령 정보를 제공 합니다. 각 리소스에는 다음 Visual Studio 명령 테이블 (.vsct) 파일을 컴파일할 때 생성 되는 이진 데이터 (.cto) 리소스 파일을 참조 합니다. 이 통해 Visual Studio가 설치 된 모든 VSPackage를 로드 하지 않고도 병합 된 명령 집합, 메뉴 및 도구 모음을 제공 합니다.  
  
### <a name="command-organization"></a>명령 조직  
 환경에서 그룹, 우선 순위 및 메뉴 명령을 배치합니다.  
  
-   예를 들어 그룹은 관련된 명령의 논리적 모음, **잘라내기**, **복사**, 및 **붙여넣기** 명령 그룹입니다. 그룹은 메뉴에 표시 되는 명령입니다.  
  
-   우선 순위는 그룹의 개별 명령을 메뉴에 표시 되는 순서를 결정 합니다.  
  
-   메뉴 그룹에 대 한 컨테이너로 사용 합니다.  
  
 환경에서는 일부 명령, 그룹 및 메뉴에 미리 정의 합니다. 자세한 내용은 참조 [기본 명령, 그룹 및 도구 모음 배치](../../extensibility/internals/default-command-group-and-toolbar-placement.md)합니다.  
  
 명령은 기본 그룹에 할당할 수 있습니다. 주 메뉴 구조 및 명령의 위치를 제어 하는 기본 그룹은 **사용자 지정** 대화 상자. 여러 그룹;에 명령이 나타날 수 있습니다. 예를 들어 주 메뉴, 바로 가기 메뉴 및 도구 모음 명령을 수 있습니다. 자세한 내용은 참조 [어떻게 Vspackage 추가 사용자 인터페이스 요소](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)합니다.  
  
### <a name="command-routing"></a>명령 라우팅  
 호출 하 고 vspackage의 명령 라우팅 과정에서 개체 인스턴스 메서드를 호출 하는 과정에서 다릅니다.  
  
 환경 (전역)은 가장 바깥쪽 컨텍스트를 현재 선택한 내용에 기반 하는 (local) 가장 안쪽의 명령 컨텍스트에서 순서 대로 명령을 라우팅합니다. 첫 번째 명령을 실행할 수 있는 컨텍스트가 처리 하는 것입니다. 자세한 내용은 참조 [라우팅 알고리즘](../../extensibility/internals/command-routing-algorithm.md)합니다.  
  
 명령을 사용 하 여 환경 대부분의 경우에서 처리는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스입니다. 명령 라우팅 체계 명령을 처리 하는 많은 다른 개체를 통해 수 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> Microsoft ActiveX 컨트롤, 창 보기 구현, 문서 개체, 프로젝트 계층 구조, 이러한; 임의 개수의 개체에 의해 구현 될 수 있습니다. 및 VSPackage 개체 자체 (명령에 대 한 글로벌). 일부 특수 한 경우에 예를 들어, 명령 라우팅 계층에는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 인터페이스를 구현 해야 합니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[구현](../../extensibility/internals/command-implementation.md)|VSPackage에서 명령을 구현 하는 방법을 설명 합니다.|  
|[가용성](../../extensibility/internals/command-availability.md)|사용할 수 있는 명령을 Visual Studio 컨텍스트를 결정 하는 방법에 대해 설명 합니다.|  
|[라우팅 알고리즘이](../../extensibility/internals/command-routing-algorithm.md)|Visual Studio 명령 라우팅 아키텍처 다른 Vspackage에서 처리 명령을 사용 하는 방법을 설명 합니다.|  
|[배치 지침](../../extensibility/internals/command-placement-guidelines.md)|Visual Studio 환경에서 명령을 배치 하는 방법을 제안 합니다.|  
|[VSPackage에서 사용자 인터페이스 요소를 추가하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)|Vspackage는 Visual Studio 명령 아키텍처 수 최대한 활용 하는 방법을 설명 합니다.|  
|[기본 명령, 그룹 및 도구 모음 배치](../../extensibility/internals/default-command-group-and-toolbar-placement.md)|Vspackage Visual Studio에 포함 된 명령 수 최대한 활용 하는 방법을 설명 합니다.|  
|[VSPackage 관리](../../extensibility/managing-vspackages.md)|Visual Studio에서 Vspackage를 로드 하는 방식을 설명 합니다.|  
|[Visual Studio 명령 테이블(.Vsct) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)|레이아웃 및 모양을 Vspackage의 명령에 대해 설명 하는 데 사용 되는 XML 기반.vsct 파일에 대 한 정보를 제공 합니다.|