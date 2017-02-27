---
title: "VS 셸 VSPackage 파일 위치를 지정합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "관리 되는 VSPackages 파일 위치"
  - "Vspackage, 관리 되는 패키지 파일 위치"
ms.assetid: beb8607a-4183-4ed2-9ac8-7527f11513b1
caps.latest.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 20
---
# VS 셸 VSPackage 파일 위치를 지정합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] VSPackage를 로드 하는 DLL 어셈블리를 찾을 수 있어야 합니다. 다음 표에 설명 된 대로 다양 한 방법으로를 찾을 수 있습니다.  
  
|메서드|설명|  
|---------|--------|  
|코드 베이스 레지스트리 키를 사용 합니다.|코드 베이스 키를 사용할 수 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 모든 정규화 된 파일 경로에서 VSPackage 어셈블리를 로드 합니다. 키의 값에는 DLL에 파일 경로 여야 합니다. 이 하는 가장 좋은 방법은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 패키지 어셈블리를 로드 합니다. 이 기술은 때로는 라고는 "코드 베이스\/개인 설치 디렉터리 기술입니다." 등록 하는 동안 코드 베이스의 값 통해 전달 됩니다 등록 특성 클래스의 인스턴스는 <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.RegistrationContext> 유형입니다.|  
|DLL에 배치 된 **PrivateAssemblies** 디렉터리입니다.|에 어셈블리는 **PrivateAssemblies** 의 하위 디렉터리는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디렉터리입니다. 어셈블리에 있는 **PrivateAssemblies** 는 자동으로 검색 되지만에 표시 되지 않는 **참조 추가** 대화 상자입니다. 차이 **PrivateAssemblies** 및 **PublicAssemblies** 이 어셈블리에서 **PublicAssemblies** 에 열거 된는 **참조 추가** 대화 상자입니다. "코드 베이스\/개인 installation directory" 기법을 사용 하지 않도록 선택한 경우에 설치 하도록는 **PrivateAssemblies** 디렉터리입니다.|  
|강력한 이름의 어셈블리와 어셈블리 레지스트리 키를 사용 합니다.|어셈블리 키를 명시적으로 직접 사용할 수 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 라는 VSPackage 어셈블리를 강력한 로드 합니다. 키의 값에는 어셈블리의 강력한 이름 이어야 합니다.|  
|DLL에 배치 된 **PublicAssemblies** 디렉터리입니다.|마지막으로, 어셈블리 배치 될 수도 있으며에 **PublicAssemblies** 하위 디렉터리입니다. 어셈블리에 있는 **PublicAssemblies** 는 자동으로 검색 하 고 나타납니다는 **참조 추가** 대화 상자에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.<br /><br /> VSPackage 어셈블리에만 배치 해야는 **PublicAssemblies** 디렉터리가 포함 된 경우 다른 VSPackage 개발자가 다시 사용 하려고 하는 구성 요소를 관리 합니다. 대부분의 어셈블리에는이 조건을 충족 하지 않습니다.|  
  
> [!NOTE]
>  모든 종속 어셈블리에 대 한 강력한 이름 지정, 서명 된 어셈블리를 사용 합니다. 이러한 어셈블리는 고유한 디렉터리 또는 전역 어셈블리 캐시 \(GAC\)에 설치 해야 합니다. 이 개체의 기본 파일 이름은, 약한 이름 바인딩을 라고 하는 어셈블리를 사용 하 여 충돌 방지 됩니다.