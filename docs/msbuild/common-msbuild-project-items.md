---
title: "Common MSBuild Project Items | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MSBuild, common project items"
ms.assetid: 1eba3721-cc12-4b80-9987-84923ede5e2e
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# Common MSBuild Project Items
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서 항목은 하나 이상의 파일에 대한 명명된 참조입니다.  항목에는 파일 이름, 경로 및 버전 번호와 같은 메타데이터가 포함됩니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 모든 프로젝트 형식에는 공통된 여러 항목이 있습니다.  이러한 항목은 파일 microsoft.build.commontypes.xsd에 정의되어 있습니다.  
  
## 공통 항목  
 다음은 모든 공통 프로젝트 항목의 목록입니다.  
  
### 참조  
 프로젝트의 어셈블리\(관리\) 참조를 나타냅니다.  
  
|항목 이름|설명|  
|-----------|--------|  
|HintPath|선택적 문자열입니다.  어셈블리의 상대 또는 절대 경로입니다.|  
|이름|선택적 문자열입니다.  어셈블리의 표시 이름\(예: "System.Windows.Forms"\)입니다.|  
|FusionName|선택적 문자열입니다.  항목에 단순 또는 강력한 Fusion 이름을 지정합니다.<br /><br /> 이 특성이 있는 경우 Fusion 이름을 알기 위해 어셈블리 파일을 열 필요가 없으므로 시간을 절약할 수 있습니다.|  
|SpecificVersion|선택적 부울입니다.  Fusion 이름의 버전만 참조할지 여부를 지정합니다.|  
|별칭|선택적 문자열입니다.  참조에 대한 별칭입니다.|  
|전용|선택적 부울입니다.  참조를 출력 폴더에 복사할지 여부를 지정합니다.  이 특성은 Visual Studio IDE에 있는 참조의 **로컬 복사** 속성과 일치합니다.|  
  
### COMReference  
 프로젝트의 COM\(비관리\) 구성 요소 참조를 나타냅니다.  
  
|항목 이름|설명|  
|-----------|--------|  
|이름|선택적 문자열입니다.  구성 요소의 표시 이름입니다.|  
|Guid|선택적 문자열입니다.  구성 요소의 GUID로, {12345678\-1234\-1234\-1234\-1234567891234} 형식을 갖습니다.|  
|VersionMajor|선택적 문자열입니다.  구성 요소 버전 번호의 주 버전 부분입니다.  예를들어 전체 버전 번호가 "5.46"이면 "5"입니다.|  
|VersionMinor|선택적 문자열입니다.  구성 요소 버전 번호의 부 버전 부분입니다.  예를들어 전체 버전 번호가 "5.46"이면 "46"입니다.|  
|LCID|선택적 문자열입니다.  구성 요소의 LocaleID입니다.|  
|WrapperTool|선택적 문자열입니다.  구성 요소에 사용되는 래퍼 도구의 이름\(예: "tlbimp"\)입니다.|  
|Isolated|선택적 부울입니다.  등록이 필요 없는 구성 요소인지 여부를 지정합니다.|  
  
### COMFileReference  
 ResolvedComreference 대상에 공급되는 형식 라이브러리 목록을 나타냅니다.  
  
|항목 이름|설명|  
|-----------|--------|  
|WrapperTool|선택적 문자열입니다.  구성 요소에 사용되는 래퍼 도구의 이름\(예: "tlbimp"\)입니다.|  
  
### NativeReference  
 네이티브 매니페스트 파일 또는 이러한 파일에 대한 참조를 나타냅니다.  
  
|항목 이름|설명|  
|-----------|--------|  
|이름|필수 문자열입니다.  매니페스트 파일의 기본 이름입니다.|  
|HintPath|필수 문자열입니다.  매니페스트 파일의 상대 경로입니다.|  
  
### ProjectReference  
 다른 프로젝트에 대한 참조를 나타냅니다.  
  
|항목 이름|설명|  
|-----------|--------|  
|이름|선택적 문자열입니다.  참조의 표시 이름입니다.|  
|Project|선택적 문자열입니다.  참조의 GUID로, {12345678\-1234\-1234\-1234\-1234567891234} 형식을 갖습니다.|  
|패키지|선택적 문자열입니다.  참조되는 프로젝트 파일의 경로입니다.|  
  
### Compile  
 컴파일러에 대한 소스 파일을 나타냅니다.  
  
|항목 이름|설명|  
|-----------|--------|  
|DependentUpon|선택적 문자열입니다.  올바르게 컴파일하기 위해 이 파일이 의존하는 파일을 지정합니다.|  
|AutoGen|선택적 부울입니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE\(통합 개발 환경\)에서 프로젝트를 위해 해당 파일이 생성되었는지 여부를 나타냅니다.|  
|링크|선택적 문자열입니다.  파일이 물리적으로 프로젝트 파일의 영향 범위 밖에 있을 때 표시할 표기 경로입니다.|  
|표시|선택적 부울입니다.  **의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]솔루션 탐색기**에 파일을 표시할지 여부를 나타냅니다.|  
|CopyToOutputDirectory|선택적 문자열입니다.  출력 디렉터리에 파일을 복사할지 여부를 결정합니다.  값:<br /><br /> 1.  Never<br />2.  Always<br />3.  PreserveNewest|  
  
### EmbeddedResource  
 생성된 어셈블리에 포함될 리소스를 나타냅니다.  
  
|항목 이름|설명|  
|-----------|--------|  
|DependentUpon|선택적 문자열입니다.  올바르게 컴파일하기 위해 이 파일이 종속되는 파일을 지정합니다.|  
|Generator|필수 문자열입니다.  이 항목에서 실행되는 파일 생성기의 이름입니다.|  
|LastGenOutput|필수 문자열입니다.  이 항목에서 실행된 모든 파일 생성기가 만든 파일의 이름입니다.|  
|CustomToolNamespace|필수 문자열입니다.  이 항목에서 실행되는 모든 파일 생성기가 코드를 만들어야 하는 네임스페이스입니다.|  
|링크|선택적 문자열입니다.  파일이 물리적으로 프로젝트의 영향 범위 밖에 있을 때 이 표기 경로가 표시됩니다.|  
|표시|선택적 부울입니다.  **의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]솔루션 탐색기**에 파일을 표시할지 여부를 나타냅니다.|  
|CopyToOutputDirectory|선택적 문자열입니다.  출력 디렉터리에 파일을 복사할지 여부를 결정합니다.  값:<br /><br /> 1.  Never<br />2.  Always<br />3.  PreserveNewest|  
|LogicalName|필수 문자열입니다.  포함된 리소스의 논리적 이름입니다.|  
  
### Content  
 프로젝트로 컴파일되지 않지만 프로젝트에 포함되거나 함께 게시될 수 있는 파일을 나타냅니다.  
  
|항목 이름|설명|  
|-----------|--------|  
|DependentUpon|선택적 문자열입니다.  올바르게 컴파일하기 위해 이 파일이 의존하는 파일을 지정합니다.|  
|Generator|필수 문자열입니다.  이 항목에서 실행되는 파일 생성기의 이름입니다.|  
|LastGenOutput|필수 문자열입니다.  이 항목에서 실행된 모든 파일 생성기가 만든 파일의 이름입니다.|  
|CustomToolNamespace|필수 문자열입니다.  이 항목에서 실행되는 모든 파일 생성기가 코드를 만들어야 하는 네임스페이스입니다.|  
|링크|선택적 부울입니다.  **의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]솔루션 탐색기**에 파일을 표시할지 여부를 나타냅니다.|  
|PublishState|필수 문자열입니다.  콘텐츠의 게시 상태로 다음 중 하나입니다.<br /><br /> -   기본<br />-   Included<br />-   Excluded<br />-   DataFile<br />-   필수 조건|  
|IsAssembly|선택적 부울입니다.  파일이 어셈블리인지 여부를 지정합니다.|  
|표시|선택적 부울입니다.  **의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]솔루션 탐색기**에 파일을 표시할지 여부를 나타냅니다.|  
|CopyToOutputDirectory|선택적 문자열입니다.  출력 디렉터리에 파일을 복사할지 여부를 결정합니다.  값:<br /><br /> 1.  Never<br />2.  Always<br />3.  PreserveNewest|  
  
### 없음  
 빌드 프로세스에서 역할이 없는 파일을 나타냅니다.  
  
|항목 이름|설명|  
|-----------|--------|  
|DependentUpon|선택적 문자열입니다.  올바르게 컴파일하기 위해 이 파일이 의존하는 파일을 지정합니다.|  
|Generator|필수 문자열입니다.  이 항목에서 실행되는 파일 생성기의 이름입니다.|  
|LastGenOutput|필수 문자열입니다.  이 항목에서 실행된 모든 파일 생성기가 만든 파일의 이름입니다.|  
|CustomToolNamespace|필수 문자열입니다.  이 항목에서 실행되는 모든 파일 생성기가 코드를 만들어야 하는 네임스페이스입니다.|  
|링크|선택적 문자열입니다.  파일이 물리적으로 프로젝트의 영향 범위 밖에 있을 때 표시될 표기 경로입니다.|  
|표시|선택적 부울입니다.  **의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]솔루션 탐색기**에 파일을 표시할지 여부를 나타냅니다.|  
|CopyToOutputDirectory|선택적 문자열입니다.  출력 디렉터리에 파일을 복사할지 여부를 결정합니다.  값:<br /><br /> 1.  Never<br />2.  Always<br />3.  PreserveNewest|  
  
### BaseApplicationManifest  
 빌드에 대한 기본 응용 프로그램 매니페스트를 나타내며 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 보안 정보를 포함합니다.  
  
### CodeAnalysisImport  
 가져올 FxCop 프로젝트를 나타냅니다.  
  
### 가져오기  
 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러가 네임스페이스를 가져올 어셈블리를 나타냅니다.  
  
## 참고 항목  
 [Common MSBuild Project Properties](../msbuild/common-msbuild-project-properties.md)