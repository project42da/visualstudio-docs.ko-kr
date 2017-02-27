---
title: "레지스트리에 도구 창 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도구 창에 등록"
ms.assetid: c4bb8add-7148-49e4-a377-01d059fd5524
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 레지스트리에 도구 창
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

도구 창을 제공 Vspackages에 등록 해야 합니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 으로 도구 창의 공급자입니다.  Visual Studio 패키지 템플릿을 사용 하 여 만든 도구 창은 기본적으로 이렇게 합니다.  도구 창의 공급자 기본 도구 창 크기 및 위치를 창의 도구 창 및 도킹 스타일으로 사용 되는 GUID 표시 유형 특성을 지정 하는 시스템 레지스트리 키가 있습니다.  
  
 개발 하는 동안 소스 코드에 특성을 추가 하 고 다음 결과 어셈블리를 대상 RegPkg.exe 유틸리티를 실행 하 여 도구 창을 관리 도구 창의 공급자를 등록 합니다.  자세한 내용은 [등록 하는 도구 창](../extensibility/registering-a-tool-window.md)를 참조하십시오.  
  
## 관리 되지 않는 도구 창의 공급자를 등록 하는 중  
 관리 되지 않는 도구 창의 공급자와 등록 해야 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ToolWindows 섹션에서 시스템 레지스트리를 합니다.  다음과 같은.reg 파일 조각을 동적 도구 창을 어떻게 등록 된 보여 줍니다.  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<version number>\ToolWindows\{f0e1e9a1-9860-484d-ad5d-367d79aabf55}]  
@="{01069cdd-95ce-4620-ac21-ddff6c57f012}"  
"Name"="Microsoft.Samples.VisualStudio.IDE.ToolWindow.DynamicWindowPane"  
"Float"="250, 250, 410, 430"  
"DontForceCreate"=dword:00000001  
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\ToolWindows\{f0e1e9a1-9860-484d-ad5d-367d79aabf55}\Visibility]  
"{f1536ef8-92ec-443c-9ed7-fdadf150da82}"=dword:00000000  
```  
  
 위의 예제에서 첫 번째 키에서 버전 번호를 버전입니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 7.1, 8.0 등과 같은 도구 창의 창 \(DynamicWindowPane\)의 GUID {f0e1e9a1\-9860\-484d\-ad5d\-367d79aabf55} 하위 키입니다 및 기본값은 {01069cdd\-95ce\-4620\-ac21\-ddff6c57f012}는 VSPackage 도구 창을 제공 하는 GUID입니다.  Float과 DontForceCreate 하위 키에 대 한 설명은 참조 하십시오. [도구 창 표시 구성](../extensibility/tool-window-display-configuration.md).  
  
 두 번째 선택적 키 ToolWindows\\Visibility, Guid 도구 창을 볼 수 있도록 요구 하는 명령 지정 합니다.  이 경우 지정 된 명령이 있습니다.  자세한 내용은 [도구 창 표시 구성](../extensibility/tool-window-display-configuration.md)를 참조하십시오.  
  
## 참고 항목  
 [VSPackage Essentials](../misc/vspackage-essentials.md)