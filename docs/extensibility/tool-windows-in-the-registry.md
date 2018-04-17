---
title: 도구 창을 레지스트리에 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- tool windows, registering
ms.assetid: c4bb8add-7148-49e4-a377-01d059fd5524
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 234a3f50865e77f2c6b5a4057e6766b26d7ff521
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="tool-windows-in-the-registry"></a>레지스트리에서 도구 창
도구 창을 제공 하는 Vspackage를 등록 해야 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 마찬가지로 도구 창 공급자입니다. Visual Studio 패키지 템플릿을 사용 하 여 만든 도구 창은 기본적으로이 작업을 수행 합니다. 도구 창 공급자는 기본 도구 창 크기 및 위치, 도구 창 및 도킹 스타일으로 사용 되는 창의 GUID와 같은 표시 유형 특성을 지정 하는 시스템 레지스트리 키 있습니다.  
  
 관리 되는 도구 창 공급자는 개발 하는 동안 소스 코드에 특성을 추가 하 고 다음 결과 어셈블리에서 RegPkg.exe 유틸리티가 실행 하 여 도구 창을 등록 합니다. 자세한 내용은 참조 [도구 창을 등록](../extensibility/registering-a-tool-window.md)합니다.  
  
## <a name="registering-unmanaged-tool-window-providers"></a>관리 되지 않는 도구 창 공급자를 등록 하는 중  
 관리 되지 않는 도구 창 공급자를 등록 해야 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 는 시스템 레지스트리의 ToolWindows 섹션에 있습니다. 다음.reg 파일 조각은 동적 도구 창이 수 등록 하는 방법을 보여 줍니다.  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<version number>\ToolWindows\{f0e1e9a1-9860-484d-ad5d-367d79aabf55}]  
@="{01069cdd-95ce-4620-ac21-ddff6c57f012}"  
"Name"="Microsoft.Samples.VisualStudio.IDE.ToolWindow.DynamicWindowPane"  
"Float"="250, 250, 410, 430"  
"DontForceCreate"=dword:00000001  
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\ToolWindows\{f0e1e9a1-9860-484d-ad5d-367d79aabf55}\Visibility]  
"{f1536ef8-92ec-443c-9ed7-fdadf150da82}"=dword:00000000  
```  
  
 위의 예에서 첫 번째 키, 버전 번호는 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]도구 창 (DynamicWindowPane) 및 기본 값 {GUID 7.1 또는 8.0, {f0e1e9a1-9860-484d-ad5d-367d79aabf55} 하위 키와 같은, 01069cdd-95ce-4620-ac21-ddff6c57f012}에 도구 창을 제공 하는 VSPackage의 GUID입니다. 참조에 대 한 설명은 Float 및 DontForceCreate 하위 키 [도구 창 디스플레이 구성](../extensibility/tool-window-display-configuration.md)합니다.  
  
 두 번째 선택적 키 ToolWindows\Visibility, 도구 창을 표시할 권한이 필요한의 Guid를 지정 합니다. 이 경우 지정 된 명령이 없는 합니다. 자세한 내용은 참조 [도구 창 디스플레이 구성](../extensibility/tool-window-display-configuration.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [VSPackage](../extensibility/internals/vspackages.md)