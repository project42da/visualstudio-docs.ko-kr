---
title: "Visual Studio Library를 사용하여 VSPackages 구현 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Visual Studio Library, VSPackage 구현"
ms.assetid: 4cbac13f-2a9d-4955-b411-dad79081fdeb
caps.latest.revision: 7
caps.handback.revision: 7
manager: "douge"
---
# Visual Studio Library를 사용하여 VSPackages 구현
`IVsPackageImpl` Visual Studio 라이브러리에서 클래스의 최소 구현을 제공의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> 인터페이스입니다.  `IVsPackageImpl`유지 관리 방법 중 대부분이 알아서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>.  의미 있는 구현 되도록 재정의 해야 하는 다른 방법은 다음과 같습니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.CreateTool%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.ResetDefaults%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A>  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 패키지 템플릿 여기에 나오는 모든 코드를 생성 합니다.  있는 Vspackage를 생성 하는 템플릿을 사용 하 여 시간을 절약할 수 있습니다.  
  
 일반적으로 Visual Studio 라이브러리를 사용 하 여 구현 된 패키지 ATL에서 VSPackage 클래스 상속 [CComObjectRootEx Class](/visual-cpp/atl/reference/ccomobjectrootex-class) 및 [CComCoClass Class](/visual-cpp/atl/reference/ccomcoclass-class) 및 Visual Studio 라이브러리의 IVsPackageImpl.  예를 들어, 다음 Reference.Package 샘플에서 VSPackage 클래스 선언입니다.  
  
```  
class ATL_NO_VTABLE BasicPackage :   
    public CComObjectRootEx<CComSingleThreadModel>,  
    public CComCoClass<BasicPackage, &CLSID_BasicPackage>,  
    public IVsPackageImpl<BasicPackage, &CLSID_BasicPackage>,  
    ...  
```  
  
 `IVsPackageImpl` 에 표시 되는 템플릿 매개 변수는 VSPackage 클래스 및 있는 Vspackage를 식별 하는 GUID에 대 한 포인터입니다.  
  
## QueryInterface COM 맵을 사용 하 여 지원  
 에 대 한 ATL의 지원을 위해 `QueryInterface`, 클래스를 구현 하는 인터페이스를 COM 맵에 나열 해야 합니다.  예를 들어, 다음의 COM 맵에 VSPackage 클래스 Reference.Package 샘플에 대 한입니다.  
  
```  
BEGIN_COM_MAP(BasicPackage)  
    COM_INTERFACE_ENTRY(IVsPackage)  
    ...  
END_COM_MAP()  
```  
  
 COM 맵에 대 한 자세한 내용은 참조 하십시오. [Implementing CComObjectRootEx](/visual-cpp/atl/implementing-ccomobjectrootex) 및 [COM\_INTERFACE\_ENTRY Macros](../Topic/COM_INTERFACE_ENTRY%20Macros.md).  
  
## 레지스트리 맵 등록 지원  
 Visual Studio 라이브러리 ATL 스타일을 사용합니다.RGS 파일을 사용 하 여 COM 개체 등록을 지원 합니다.  토큰 교체에서 지원할 수 있는.RGS 파일에서 Visual Studio 라이브러리 레지스트리 매핑을 사용합니다.  레지스트리 목록 기호를 대체 Id 사용 하는 문자열 테이블 리소스에 대 한 지원 등을 매핑합니다.  
  
 예를 들어, 다음 레지스트리 맵 VSPackage 클래스 Reference.Package 샘플에서입니다.  
  
```  
VSL_BEGIN_REGISTRY_MAP(IDR_BASICPACKAGE_RGS)  
    VSL_REGISTRY_MAP_GUID_ENTRY(CLSID_BasicPackage)  
    VSL_REGISTRY_RESOURCE_STRING_ENTRY(IDS_BASICPACKAGE_REGISTRY_NAME)  
    ...  
VSL_END_REGISTRY_MAP()  
```  
  
## 참고 항목  
 [VSSDK 샘플](../misc/vssdk-samples.md)