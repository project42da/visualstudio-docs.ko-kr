---
title: "Windows Installer 기본 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Windows Installer를 Vspackage"
  - "Vspackage, Windows Installer 기본 사항"
ms.assetid: 497e479b-add8-4644-870a-917f15306b97
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# Windows Installer 기본 사항
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Windows Installer 설치 및 제거 응용 프로그램 또는 사용자의 컴퓨터에서 소프트웨어 제품 \(WICs 또는 단순히 구성 요소 라고도 함\)는 Windows Installer 구성 요소 라는 단위로 이러한 작업을 수행 합니다. GUID는 설치 및 Windows Installer를 사용 하 여 설정에 대 한 계산 참조의 기본 단위는 각 WIC를 식별 합니다.  
  
 Windows Installer의 포괄적인 설명서 Platform SDK 항목을 참조 하십시오. [Windows Installer](http://msdn.microsoft.com/library/aa372866.aspx)합니다.  
  
## VSPackage를 작성합니다.  
 Windows Installer 설치, 제거 또는 제품을 복구 하 고 설치 프로그램 사용자 인터페이스 \(UI\)를 실행 해야 하는 정보가 포함 된 설치 패키지를 사용 합니다. 각 설치 패키지 설치 데이터베이스, 요약 정보 스트림 및 설치의 다양 한 부분에 대 한 데이터 스트림을 포함 하는.msi 파일이 포함 되어 있습니다. 설치 관리자를 사용 하려면 설치를 작성 해야 합니다. 구성의 개념을 중심 설치를 구성 하 고 관계형 데이터베이스에 설치 하는 방법에 대 한 정보를 저장 하는 설치 관리자 이기 때문에 광범위 하 게 설치 패키지를 작성 하는 과정은 다음 단계를 이루어집니다.  
  
1.  Side\-by\-side\-전략 및 버전 관리를 지원 하도록 제작의 설치를 계획 합니다.  
  
2.  사용자에 게 표시 하는 기능을 식별 합니다.  
  
3.  구성 요소에는 VSPackage 및 종속성을 구성 합니다.  
  
4.  설치 데이터베이스를 정보를 채웁니다.  
  
5.  설치 패키지의 유효성을 검사 합니다.  
  
 이 설명서는 주로 프로세스의 첫 번째 및 세 번째 단계와 관련 되어 있습니다. 이 단계를 구성 하면 VSPackage 기능 WICs 프로그램 버전 관리 및 서비스 전략 고려 하기 위해 이후 버전의 프레임 수 있도록 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 나머지 세 단계는 Platform SDK에 대 한 Windows Installer 설명서에 자세히 설명 합니다.  
  
## 주요 용어  
 다음은 Windows Installer 기술에 관련 된 주요 항목의 정의입니다.  
  
 리소스  
 파일, 레지스트리 키, 바로 가기, 또는 등 컴퓨터에 설치 될 수 있습니다. 이러한 리소스는 Windows Installer 구성 요소에 논리적으로 그룹화 됩니다.  
  
 Windows Installer 구성 요소 \(WIC\)  
 설치 및 단위를 제거 되는 관련된 리소스의 논리적 그룹화를 나타내는 설치의 기본 단위입니다. Windows Installer 구성 요소가 고유한 구성 요소 ID 또는 GUID로 식별 됩니다. 또한 Windows Installer WIC 수준에서 계산 참조를 유지 합니다. 최대 버전 관리 유연성에 대 한 DLL 같은 둘 이상의 기본 리소스 지정된 WIC에 포함 합니다. 참고 있습니다 식별 하 고는 WIC를 채우는, GUID를 지정 하 고 배포한 후 해당 구성을 변경할 수 없습니다. 자세한 내용은 참조 [구성 요소를 응용 프로그램 구성](http://msdn.microsoft.com/library/aa370561.aspx)합니다.  
  
 패키지 \(재배포 가능 패키지\)  
 이 파일을 가리킬 수 있습니다.msi 파일 및 외부 소스 파일의 구성 된 배포의 단위입니다. 패키지를 실행 하는 UI를 설치 하거나 응용 프로그램을 제거 해야 하는 모든 정보를 포함 합니다.  
  
 .msi 파일  
 응용 프로그램을 설치 하는 데 필요한 데이터 및 지침을 포함 하는 COM\-구조적 저장소 파일입니다. 모든 패키지에는 하나 이상의.msi 파일에 포함 되어 있습니다. .Msi 파일에는 설치 관리자 데이터베이스, 요약 정보 스트림 및 가능성이 있는 하나 이상의 변환 및 내부 소스 파일이 포함 되어 있습니다. 파일을 설치할 수 캐비닛으로 압축 및.msi 파일에 스트림에 저장 또는 저장, 압축 하거나 압축 되지 않은 원본 미디어에서.msi 파일의 외부 합니다. 자세한 내용은 참조 [Windows Installer 파일 확장명](http://msdn.microsoft.com/library/aa372842\(VS.85\).aspx)합니다.  
  
## Windows Installer 규칙 적용  
 두 가지 규칙 설정의 구성 요소를 통해 리소스의 배포를 확인합니다. 하나의 규칙 집합 작성자 설치는 두 번째 집합을 적용 해야 하는 동안 자체는 Windows installer 유지 됩니다.  
  
> [!NOTE]
>  Windows Installer 규칙의 적용에는.msi 파일에 대 한 유효성 검사를 실행 하는 경우에 발생 합니다. 그럼에도 불구 하 고 유용한 정보로 이러한 규칙을 처리할 있습니다 주의가 요구 됩니다. 자세한 내용은 참조 [설치 데이터베이스의 유효성을 검사](http://msdn.microsoft.com/library/aa372477\(VS.85\).aspx) 및 [패키지 유효성 검사](http://msdn.microsoft.com/library/aa370569\(VS.85\).aspx)합니다.  
  
#### 설치 관리자 부여 규칙  
  
-   지정된 된 구성 요소에 있는 모든 파일을 동일한 디렉터리에 설치 되어야 합니다. 반대로, 별개의 폴더에 설치 된 파일은 구성 요소 구분에 속해야 합니다.  
  
-   구성 요소당 키 경로 한 개만 있을 수 있습니다. 키 경로 단순히 파일 또는 레지스트리 키 전체 구성 요소를 나타냅니다.  
  
#### 구성 요소 공급자 책임  
  
-   이후 버전에서는 함께 별도로 제공 될 수 있는 두 리소스는 별도 구성 요소에 존재 해야 합니다. 이러한 리소스 별도로 제공 되지 것입니다 확신 하는 경우에 리소스 동일한 구성 요소를 그룹화 해야 합니다. 실제로 것이 좋습니다 모든 기본 리소스 \(예: Dll\) 별도 WICs에 항상 존재 합니다. 자세한 내용은 참조 [설치 관리자 구성 요소 정의](http://msdn.microsoft.com/library/aa368269\(VS.85\).aspx)합니다.  
  
-   둘 이상의 WIC에 버전이 지정 된 리소스가 제공 적 안 됩니다.  
  
## 참고 항목  
 [구성 요소 규칙을 위반 하는 경우 어떻게 됩니까?](http://msdn.microsoft.com/library/aa372795\(VS.85\).aspx)