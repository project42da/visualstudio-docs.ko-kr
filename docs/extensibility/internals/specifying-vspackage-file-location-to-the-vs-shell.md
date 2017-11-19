---
title: "VS Shell VSPackage 파일 위치를 지정 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed VSPackages, file location
- VSPackages, managed package file location
ms.assetid: beb8607a-4183-4ed2-9ac8-7527f11513b1
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b987d5e88bcbcf02bfd80ddf5c3ed0d67a149b53
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="specifying-vspackage-file-location-to-the-vs-shell"></a>VS Shell VSPackage 파일 위치를 지정합니다.
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]VSPackage를 로드 하는 DLL 어셈블리를 찾을 수 있어야 합니다. 다음 표에 설명 된 대로 다양 한 방법으로를 찾을 수 있습니다.  
  
|메서드|설명|  
|------------|-----------------|  
|코드 베이스 레지스트리 키를 사용 합니다.|코드 베이스 키를 직접 사용할 수 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 모든 정규화 된 파일 경로에서 VSPackage 어셈블리를 로드 합니다. 키의 값에는 DLL에 파일 경로 여야 합니다. 이 하는 가장 좋은 방법은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 패키지 어셈블리를 로드 합니다. 이 기술은 때때로 이라고는 "코드 베이스/개인 설치 디렉터리 기술입니다." 등록 하는 동안 값의 코드 베이스 전달 등록 특성 클래스의 인스턴스를 통해는 <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.RegistrationContext> 유형입니다.|  
|DLL에 배치 된 **PrivateAssemblies** 디렉터리입니다.|에 어셈블리는 **PrivateAssemblies** 의 하위 디렉터리는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디렉터리입니다. 어셈블리에 배치 **PrivateAssemblies** 는 자동으로 검색 하지만에 표시 되지 않습니다는 **참조 추가** 대화 상자. 차이 **PrivateAssemblies** 및 **PublicAssemblies** 어셈블리는에 **PublicAssemblies** 에 열거는 **참조 추가**  대화 상자. "코드 베이스/개인 설치 디렉터리" 기법을 사용 하지 않도록 선택한 경우에 설치 해야는 **PrivateAssemblies** 디렉터리입니다.|  
|강력한 이름의 어셈블리 및 어셈블리 레지스트리 키를 사용 합니다.|어셈블리 키를 명시적으로 직접 사용할 수 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 이름의 VSPackage 어셈블리를 강력한 로드 합니다. 키의 값에는 어셈블리의 강력한 이름 이어야 합니다.|  
|DLL에 배치 된 **PublicAssemblies** 디렉터리입니다.|마지막으로, 어셈블리 또한으로 배치 될 수는 **PublicAssemblies** 하위 디렉터리입니다. 어셈블리에 배치 **PublicAssemblies** 는 자동으로 검색 및에 표시 됩니다는 **참조 추가** 대화 상자에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.<br /><br /> VSPackage 어셈블리에만 배치 해야는 **PublicAssemblies** 디렉터리가 포함 된 경우 다른 VSPackage 개발자가 재사용 하도록 설계 된 구성 요소를 관리 합니다. 대부분의 어셈블리에는이 조건을 충족 하지 않습니다.|  
  
> [!NOTE]
>  모든 종속 어셈블리의 강력한 이름 지정, 서명 된 어셈블리를 사용 합니다. 이러한 어셈블리 자신의 디렉터리 또는 전역 어셈블리 캐시 (GAC)에 설치 해야 합니다. 이 동일한 기본 파일 이름을 약한 이름 바인딩을 라고 하는 어셈블리와 충돌을 방지 합니다.