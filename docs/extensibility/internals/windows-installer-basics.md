---
title: Windows Installer 기본 사항 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Windows Installer, VSPackages
- VSPackages, Windows Installer basics
ms.assetid: 497e479b-add8-4644-870a-917f15306b97
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8fba35aba1e1947ee4eeeb59ca2225253e2aa3a8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="windows-installer-basics"></a>Windows Installer 기본 사항
Windows Installer 설치 및 Windows Installer 구성 요소가 (WICs 또는 정당한 구성 요소 라고도 함) 라는 단위로 이러한 작업을 수행 합니다. 응용 프로그램 또는 사용자의 컴퓨터에 소프트웨어 제품 제거 합니다. GUID는 설치 및 Windows Installer를 사용 하 여 설치를 사용한 참조의 기본 단위를 각 WIC를 식별 합니다.  
  
 Windows Installer 포괄적 설명서 Platform SDK 항목을 참조 하십시오. [Windows Installer](http://msdn.microsoft.com/library/aa372866.aspx)합니다.  
  
## <a name="authoring-a-vspackage"></a>VSPackage를 작성합니다.  
 Windows Installer를 설치, 제거 또는 제품을 복구 하 고 설치 사용자 인터페이스 (UI)를 실행 해야 하는 정보가 포함 된 설치 패키지를 사용 합니다. 각 설치 패키지 설치 데이터베이스, 요약 정보 스트림 및 설치의 다양 한 부분에 대 한 데이터 스트림을 포함 하는.msi 파일을 포함 합니다. 설치 관리자를 사용 하려면 설치를 제작 해야 합니다. 설치 관리자는 구성 요소 개념과 관련 설치를 구성 하 고 관계형 데이터베이스에 설치 하는 방법에 대 한 정보를 저장, 때문에 광범위 하 게 설치 패키지를 작성 하는 과정은 다음 단계를 이루어집니다.  
  
1.  나란히 전략 및 버전 관리를 지원 하도록 작성 하면 설치를 계획 합니다.  
  
2.  사용자에 게 표시 되는 기능을 식별 합니다.  
  
3.  구성 요소에는 VSPackage 및 종속성을 구성 합니다.  
  
4.  설치 정보로 데이터베이스를 채웁니다.  
  
5.  설치 패키지의 유효성을 검사 합니다.  
  
 이 설명서는 프로세스의 첫 번째 및 세 번째 단계 주로 관여 합니다. 이 단계에서 구성한 VSPackage 기능 WICs에 프로그램 버전 관리 및 서비스 전략의 이후 버전을 설명 하기 위해 프레임 수 있도록 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 나머지 세 단계는 Platform SDK에서 Windows Installer 설명서에 자세히 설명 합니다.  
  
## <a name="key-terms"></a>주요 용어  
 다음은 Windows Installer 기술을 관련 된 주요 용어를 정의 합니다.  
  
 리소스  
 파일, 레지스트리 키, 바로 가기 또는 등 컴퓨터에 설치할 수 있습니다. 이러한 리소스는 Windows Installer 구성 요소에 논리적으로 그룹화 됩니다.  
  
 Windows Installer 구성 요소 (WIC)  
 설치 되 고 하나의 단위로 제거 될 수 있는 관련된 리소스의 논리적 그룹화를 나타내는 설치의 기본 단위입니다. Windows Installer 구성 요소에 고유한 구성 요소 ID 또는 GUID로 식별 됩니다. 또한 Windows Installer WIC 수준에서 계산 참조를 유지 합니다. 버전 관리 최대 유연성 주어진된 WIC에 DLL 같은 둘 이상의 기본 리소스를 포함 합니다. 참고 하면 식별 한 WIC를 채우는, GUID를 지정 하 고, 후 구성을 변경할 수 없습니다. 자세한 내용은 참조 [구성 응용 프로그램 구성 요소에](http://msdn.microsoft.com/library/aa370561.aspx)합니다.  
  
 패키지 (재배포 가능 패키지)  
 이 파일 가리킬 수 있습니다는.msi 파일 및 외부 소스 파일 구성 된 배포의 단위입니다. 패키지는 Windows Installer UI를 실행 하 고 설치 하거나 응용 프로그램을 제거 하는 모든 정보를 포함 합니다.  
  
 .msi 파일  
 지침 및 응용 프로그램을 설치 하는 데 필요한 데이터를 포함 하는 COM-구조적 저장소 파일입니다. 모든 패키지에는.msi 파일을 하나 이상 포함합니다. .Msi 파일에는 설치 관리자 데이터베이스, 요약 정보 스트림 및 수 있는 하나 이상의 변환 및 내부 소스 파일이 포함 되어 있습니다. 파일을 설치할 수 캐비닛으로 압축 되었고 및.msi 파일에 스트림을에 저장 또는 저장, 압축 하거나 압축 되지 않은 원본 미디어에서.msi 파일 외부 하십시오. 자세한 내용은 참조 [Windows Installer 파일 확장명](http://msdn.microsoft.com/library/aa372842\(VS.85\).aspx)합니다.  
  
## <a name="windows-installer-rules-enforcement"></a>Windows Installer 규칙 적용  
 두 규칙 집합이 설정의 구성 요소를 통해 리소스의 배포를 결정합니다. 하나의 규칙 집합 작성자 설치 두 번째 집합을 적용 해야 하는 동안 자체에 Windows installer 유지 관리 됩니다.  
  
> [!NOTE]
>  Windows Installer 규칙의 적용에는.msi 파일의 유효성 검사를 실행 하는 경우에 발생 합니다. 그럼에도 불구 하 고 최선의 구현 방법으로 이러한 규칙을 처리 하도록 하면 주의가 요구 됩니다. 자세한 내용은 참조 [설치 데이터베이스 유효성 검사](http://msdn.microsoft.com/library/aa372477\(VS.85\).aspx) 및 [패키지 유효성 검사](http://msdn.microsoft.com/library/aa370569\(VS.85\).aspx)합니다.  
  
#### <a name="installer-enforced-rules"></a>설치 관리자 부여 규칙  
  
-   지정 된 구성 요소에 있는 모든 파일은 동일한 디렉터리에 설치 되어야 합니다. 반대로, 별개의 폴더에 설치 된 파일 구성 요소 구분에 속해야 합니다.  
  
-   구성 요소당 하나의 키 경로가 있을 수 있습니다. 키 경로 단순히 파일 또는 레지스트리 키 전체 구성 요소를 나타냅니다.  
  
#### <a name="component-provider-responsibilities"></a>구성 요소 공급자의 책임  
  
-   이후 버전에서 개별적으로 함께 제공 될 수 있는 두 개의 리소스는 별도 구성 요소에 존재 해야 합니다. 리소스 동일한 구성 요소를 그룹화 되어야만 확신할 때 이러한 리소스 별도로 제공 되지 것입니다. 실제로 것이 좋습니다 모든 기본 리소스 (예: Dll) 별도 WICs에 항상 존재 합니다. 자세한 내용은 참조 [설치 관리자 구성 요소 정의](http://msdn.microsoft.com/library/aa368269\(VS.85\).aspx)합니다.  
  
-   버전이 없는 리소스에 둘 이상의 WIC 제공도 안 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [구성 요소 규칙을 위반 하는 경우 어떻게 됩니까?](http://msdn.microsoft.com/library/aa372795\(VS.85\).aspx)